<script setup>
defineProps({
    image: String,
    title:String,
    description:String
})
</script>

<template>
    <div class="group flex flex-row gap-4 items-center hover:bg-gray-100 p-1 cursor-pointer">
        <img class="w-[48px] rounded-full" alt="group image" :src="image">
        <div class="group-details">
            <h1 class="font-extrabold text-xl text-black"> {{ title }}</h1>
            <p class="text-sm  text-gray-500">{{
                    description
                }}</p>
        </div>
    </div>
</template>

<style scoped>

</style>
