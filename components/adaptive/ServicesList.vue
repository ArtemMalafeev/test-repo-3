<template>
    <ul class="grid grid-cols-[repeat(auto-fill,minmax(328px,1fr))] gap-y-[128px] gap-x-8 py-5 min-[1440px]:py-[144px] min-[1440px]:flex min-[1440px]:flex-col min-[1440px]:gap-y-[128px]">
        <ServicesListItem v-for="service in services" :key="service.id" :service="service" />
    </ul>
</template>

<script setup>
import ServicesListItem from '~/components/adaptive/ServicesListItem.vue';

defineProps({
    services: Array,
});
</script>

<style scoped></style>