<template>
    <article class="flex flex-col gap-y-8">
        <div class="w-full h-[220px]">
            <img :src="`/images/adaptive/${service.image}.png`" :alt="service.alt" class="image rounded-2xl">
        </div>
        <div class="flex flex-col gap-y-6">
            <div class="flex flex-col gap-y-4">
                <h2 class="text-[32px] leading-10 tracking-[-0.03em] text-[#F9FAFB]">
                    {{ service.title }}
                </h2>
                <p class="text-lg leading-6 text-[#E5E7EB]">
                    {{ service.description }}
                </p>
            </div>
            <a class="flex items-center w-max gap-x-3 py-2.5 text-lg bg-gradient-to-r from-[#6366F1] to-[#AC54F1] text-transparent bg-clip-text"
                href="#">
                {{ service.link }}
                <span>
                    <svg width="16" height="14" viewBox="0 0 16 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M9.68869 1.5L14.5 7.00002L9.68869 12.5M14.1232 7H1.5" stroke="#AC55F2" stroke-width="2"
                            stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </span>
            </a>
        </div>
    </article>
</template>

<script setup lang="ts">

defineProps({
    service: Object,
});
</script>

<style scoped></style>