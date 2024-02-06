<template>
    <div class="w-screen h-screen relative bg-gray-100">
        <div class="absolute top-2/4 left-2/4 translate-x-[-50%] translate-y-[-50%] w-full max-w-[500px] px-[20px]">
            <form class="flex flex-col gap-y-[32px] p-5 bg-white shadow-md" @submit.prevent="submitted">
                <div class="form-group">
                    <label class="form-label" for="name">ФИО:</label>
                    <input :class="{ 'field-error': !isNameValid }" class="form-field" placeholder="Артем Малафеев"
                        v-model.trim="userData.name" id="name" name="name" type="text">
                    <p v-show="!isNameValid" class="error">Только кириллица и 2 слова</p>
                </div>

                <div class="form-group">
                    <label class="form-label" for="phone">Телефон:</label>
                    <input :class="{ 'field-error': !isPhoneValid }" class="form-field" placeholder="+79964185676"
                        v-model.trim="userData.phone" id="phone" name="phone" type="text">
                    <p v-show="!isPhoneValid" class="error">Только 12 символов и +7</p>
                </div>

                <div class="form-group">
                    <label class="form-label" for="email">Почта:</label>
                    <input class="form-field" v-model.trim="userData.email" placeholder="mrtema1999@gmail.com" id="email"
                        name="email" type="text">
                </div>

                <div class="form-group">
                    <label class="form-label" for="password">Пароль:</label>
                    <input class="form-field" v-model.trim="userData.password" id="password" name="password" type="password"
                        autocomplete="on">
                </div>

                <button :disabled="!isFormValid.value"
                    class="px-[14px] py-[8px] bg-blue-500 text-white w-max m-auto hover:bg-red-400 transition duration-150 ease-in disabled:opacity-35 disabled:cursor-not-allowed disabled:bg-slate-400"
                    type="submit">
                    Отправить форму
                </button>
            </form>
        </div>
        <UiArrows>
            <NuxtLink to="/article">
                <svg class="rotate-180" xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                    <path
                        d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                </svg>
            </NuxtLink>
            <NuxtLink to="/">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                    <path
                        d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                </svg>
            </NuxtLink>
        </UiArrows>
    </div>
</template>

<script setup lang="ts">
import UiArrows from '~/components/UiArrows.vue';

const emailCheckRegExp = /^[А-Яа-яЁё]+\s[А-Яа-яЁё]+$/;
const phoneCheckRegExp = /^\+7\d{10}$/;

const isSubmitted = ref(false);

const userData = ref({
    name: null,
    phone: null,
    email: null,
    password: null,
});

async function submitted() {
    isSubmitted.value = true;

    await $fetch('#', {
        method: 'post',
        body: {
            name: userData.value.name,
            phone: userData.value.phone,
            email: userData.value.email,
            password: userData.value.password,
        },
    });
};

const isNameValid = computed(() => {
    return userData.value.name !== null && emailCheckRegExp.test(userData.value.name);
});

const isPhoneValid = computed(() => {
    return userData.value.phone !== null && phoneCheckRegExp.test(userData.value.phone);
});

const isFormValid = computed(() => {
    return isNameValid && isPhoneValid;
});
</script>

<style scoped>
.form-group {
    @apply flex flex-col gap-y-2 relative;
}

.form-label {
    @apply text-gray-800 text-[14px];
}

.form-field {
    @apply px-[12px] py-[8px] border border-slate-400 rounded outline-none focus:border-blue-800;
}

.field-error {
    @apply border-red-600 focus:border-red-600;
}

.error {
    @apply absolute bottom-[-24px] text-pink-600 text-sm;
}
</style>