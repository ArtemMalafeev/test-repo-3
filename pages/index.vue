<template>
    <div class="min-h-screen bg-gray-200 pt-[100px]">
        <header class="text-[32px] text-center">Тестовое задание для компании "Tapigo"</header>
        <main class="relative">
            <UiArrows>
                <NuxtLink to="/form">
                    <svg class="rotate-180" xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                        <path
                            d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                    </svg>
                </NuxtLink>
                <NuxtLink to="/adaptive">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                        <path
                            d="M10 20A10 10 0 1 0 0 10a10 10 0 0 0 10 10zM8.711 4.3l5.7 5.766L8.7 15.711l-1.4-1.422 4.289-4.242-4.3-4.347z" />
                    </svg>
                </NuxtLink>
            </UiArrows>
        </main>
    </div>
</template>

<script setup lang="ts">
import UiArrows from '~/components/UiArrows.vue';
</script>

<style scoped></style>