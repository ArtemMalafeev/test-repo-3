<template>
    <div class="bg-gradient-to-b from-[#111827] to-[#1F293E]">
        <div class="max-w-[1440px] h-full mx-4 min-[1440px]:mx-auto">
            <ServicesList v-if="services" :services="services" />
            <div v-else>
                Data is Empty!
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import ServicesList from '~/components/adaptive/ServicesList.vue';

const { data: services } = await useFetch('/api/services');
</script>

<style scoped></style>