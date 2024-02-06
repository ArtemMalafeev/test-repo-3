<template>
    <ul class="grid grid-cols-[repeat(auto-fill,minmax(328px,1fr))] gap-y-[128px] gap-x-8 py-5">
        <li v-for="service in services" :key="service.id">
            <ServicesListItem :service="service" />
        </li>
    </ul>
</template>

<script setup lang="ts">
import ServicesListItem from '~/components/adaptive/ServicesListItem.vue';

defineProps({
    services: Array,
});
</script>

<style scoped></style>