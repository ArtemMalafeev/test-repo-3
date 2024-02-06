<template>
    <div class="min-h-screen bg-gradient-to-b from-[#111827] to-[#1F293E]">
        <div class="max-w-[1440px] h-full mx-4 min-[1440px]:mx-auto">
            <ServicesList v-if="services" :services="services" />
            <div v-else>
                Data is Empty!
            </div>
        </div>
        <UiArrows>
            <NuxtLink to="/">
                <svg class="rotate-180" xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                    <path
                        d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                </svg>
            </NuxtLink>
            <NuxtLink to="/article">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                    <path
                        d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                </svg>
            </NuxtLink>
        </UiArrows>
    </div>
</template>

<script setup>
import UiArrows from '~/components/UiArrows.vue';
import ServicesList from '~/components/adaptive/ServicesList.vue';

const { data: services } = await useFetch('/api/services');
</script>

<style scoped></style>