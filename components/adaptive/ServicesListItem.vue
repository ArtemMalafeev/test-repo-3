<template>
    <li
        class="flex flex-col items-center w-full h-full gap-y-8 min-[1440px]:flex-row min-[1440px]:gap-x-[64px] min-[1440px]:h-[560px] min-[1440px]:even:flex-row-reverse">
        <div class="w-full h-[220px] min-[1440px]:w-[800px] min-[1440px]:flex-shrink-0 min-[1440px]:h-full">
            <img :src="`/images/adaptive/${service.image}.png`" :alt="service.alt"
                class="w-full h-full object-cover rounded-2xl">
        </div>
        <div class="relative flex flex-col gap-y-6 min-[1440px]:gap-y-[48px] min-[1440px]:px-[48px] min-[1440px]:py-[30px]">
            <div class="flex flex-col gap-y-4 min-[1440px]:gap-y-[24px]">
                <h2
                    class="text-[32px] leading-10 tracking-[-0.03em] text-[#F9FAFB] min-[1440px]:text-[48px] min-[1440px]:leading-[56px]">
                    {{ service.title }}
                </h2>
                <p class="text-lg leading-6 text-[#E5E7EB] min-[1440px]:text-[20px] min-[1440px]:leading-[30px]">
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
            <span
                class="absolute inline-block hidden min-[1440px]:block top-0 left-0 w-[45px] border-t border-l border-[#6B7280] rounded-tl-lg h-[45px] bg-transparent"></span>
            <span
                class="absolute inline-block hidden min-[1440px]:block bottom-0 right-0 w-[45px] border-b border-r rounded-br-lg border-[#6B7280] h-[45px] bg-transparent"></span>
        </div>
    </li>
</template>

<script setup>

defineProps({
    service: Object,
});
</script>

<style scoped></style>