<script setup>

import TextInput from "@/Components/TextInput.vue";
import GroupItem from "@/Components/app/GroupItem.vue";
import {ref} from "vue";

const searchKeyword = ref("");

</script>

<template>
    <div class=" border py-3 px-3 bg-white h-[400px] flex flex-col overflow-hidden rounded">
        <h1 class="text-xl  font-bold">My Groups</h1>

        <div class="search  my-3 grid place-items-center">
            <TextInput place-holder="Type to search  " class="w-full" :model-value="searchKeyword"/>
            <!--                <input type="text" name="search" id="">-->
        </div>
       <div class="mt-3 flex-1 overflow-auto">
           <div v-if="false">
               <p class="text-gray-400 p-3 text-center ">You are not joined to any groups</p>
           </div>
           <div v-else class="overflow-auto h-full flex flex-col gap-2">

               <GroupItem image="https://picsum.photos/100" title="Vue Js Developers" description="As i have hurted you, so you must handle one another."/>
               <GroupItem image="https://picsum.photos/100" title="Laravel Developers" description="When the sensor wobbles for starfleet headquarters, all species experience greatly exaggerated, spheroid crewmates."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="PHP Developers" description="Everyone just loves the creaminess of peanut butter platter marinated with thyme."/>
               <GroupItem image="https://picsum.photos/100" title="Python Developers" description="Assimilant tandem ducunt ad domesticus scutum."/>
           </div>

       </div>

    </div>
</template>

<style scoped>

</style>
