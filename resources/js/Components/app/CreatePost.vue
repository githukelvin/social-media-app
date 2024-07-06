<script setup>
import {ref} from "vue";

const postCreate = ref(false)
</script>

<template>
<div class="py-6 rounded px-3 border bg-white mb-3">
    <div @click="postCreate = true" class="select-none py-3 cursor-pointer text-md text-center px-2 text-gray-500 border-2 border-gray-200 rounded mb-3">
        Click here to create new post
    </div>
    <div class="flex flex-row justify-between" v-show="postCreate">
        <button type="submit"  class="relative rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">
            Attach Files
            <input type="file" class="absolute inset-0 opacity-0" name="files" id="file">
        </button>
        <button type="submit" class="rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">
            Submit
        </button>

    </div>
</div>
</template>

<style scoped>

</style>
