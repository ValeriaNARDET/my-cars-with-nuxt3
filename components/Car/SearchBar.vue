<template>
    <div class="font-serif text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
        <input type="text" v-model="city" class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
            :class="cityError ? 'border-red-500' : ''" placeholder="Search by city..." @keyup.enter="handleSerch()" />
        <button class="bg-sky-500 px-10 text-white" @click="handleSerch()">Search</button>
    </div>
</template>

<script setup>
const city = ref("");
const cityError = ref(false);
// const router = useRouter();
const route = useRoute();
city.value = route.params.city;

const handleSerch = () => {
    if (!city.value) {
        cityError.value = true;
    }
    console.log(city.value);
    navigateTo(`/city/${city.value}/car`)
    // router.push(`/city/${city.value}/car/${make}`)
}
// 
</script>