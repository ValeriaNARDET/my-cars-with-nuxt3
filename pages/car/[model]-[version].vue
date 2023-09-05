<template>
    <CarDetails />
    <CarAttributes />
    <CarDescription />
    <CarContacts />
</template>

<script setup>
const route = useRoute();
const { toTitleCase } = useUtilities();

useHead({
    title: toTitleCase(route.params.model)
})

definePageMeta({
    layout: "custom"
})

</script>