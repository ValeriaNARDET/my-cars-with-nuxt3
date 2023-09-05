<template>
    <div class="mt-32 flex">
        <CarSideBar />
        <NuxtPage />
    </div>
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();
const titleWord = route.params.make ? toTitleCase(route.params.make) : `in ${toTitleCase(route.params.city)}`;

useHead({
    title: `Cars ${titleWord}`
})

definePageMeta({
    layout: "custom"
})
</script>