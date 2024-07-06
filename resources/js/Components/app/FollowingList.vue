<script setup>

import TextInput from "@/Components/TextInput.vue";
import {ref} from "vue";
import FollowingItem from "@/Components/app/FollowingItem.vue";

const searchKeyword = ref("");

</script>

<template>
    <div class=" p-3 bg-white h-[400px] flex flex-col overflow-hidden rounded">
        <h1 class="text-xl font-bold">My Followings</h1>

        <div class="search my-3 grid place-items-center">
            <TextInput place-holder="Type to search  " class="w-full" :model-value="searchKeyword"/>
            <!--                <input type="text" name="search" id="">-->
        </div>
      <div class="mt-3 flex-1 overflow-auto">
          <div v-if="false">
              <p class="text-gray-400 p-3 text-center ">You dont Have friends yet</p>
          </div>
          <div v-else class="groups flex flex-col gap-2">

              <FollowingItem image="https://picsum.photos/100" title="John Doe" description="Sunt cursuses imperium clemens, barbatus spatiies."/>
              <FollowingItem image="https://picsum.photos/100" title="Jane Doe" description="Mermaids experiment with history!"/>
              <FollowingItem image="https://picsum.photos/100" title="Decoder Kel" description="Aww! Pieces o' booty are forever salty."/>
              <FollowingItem image="https://picsum.photos/100" title="Kelvin Githu" description="Wrestle and you will be remembered spiritually."/>
          </div>

      </div>

    </div>
</template>

<style scoped>

</style>
