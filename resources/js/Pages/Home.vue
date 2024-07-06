<script setup>
import { Head } from '@inertiajs/vue3';
import GroupList from "@/Components/app/GroupList.vue";
import FollowersList from "@/Components/app/FollowingList.vue";
import CreatePost from "@/Components/app/CreatePost.vue";
import PostList from "@/Components/app/PostList.vue";



</script>

<template>
    <Head title="Social Media Website" />

    <div class="lg:container mx-auto h-full grid px-4 lg:grid-cols-12 gap-3 " >

        <div class="lg:col-span-3 py-6 h-full overflow-hidden  lg:order-1">
            <GroupList/>

        </div>
        <div class="lg:col-span-3 py-6 h-full overflow-hidden   lg:order-3">
            <FollowersList/>

        </div>
        <div class="lg:col-span-6 py-6  overflow-hidden  lg:order-2">
            <create-post/>
            <post-list/>
        </div>


    </div>
</template>
