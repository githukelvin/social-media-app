<script setup>
import {Disclosure, DisclosureButton, DisclosurePanel} from "@headlessui/vue";
import { ChevronUpIcon } from '@heroicons/vue/20/solid'

defineProps({

    post:{
        type:Object,
        required:true
    },
})

function isImage(attachment){
    const mime= attachment.mime.split("/");
    return mime[0].toLowerCase() === "image"
}
</script>

<template>
<div class="rounded bg-white border p-4 shadow">
    <div class="flex  flex-row items-center gap-2 mb-3">
        <a href="javascript:void(0)">
            <img class="w-[48px] h-[48px] transition-all rounded-full object-center  border-2 hover:border-blue-400" :src="post.user.avatar" :alt="post.user.name" srcset="">

        </a>
    <div class=" flex flex-col gap-1">

            <h4 class="font-bold text-xl flex flex-row gap-2"><a href="javascript:void(0)" class="hover:underline">{{post.user.name}}</a>
              <div v-if="post.group !== null">
                  >
                  <a class="hover:underline" href="javascript:void(0)">{{post.group.name}}</a>
              </div>
            </h4>
            <p class="text-sm font-bold text-gray-400">{{post.created_at}}</p>



    </div>
    </div>

    <div class="mb-3">
        <Disclosure v-slot="{ open }">
            <div v-if="!open" v-html="post.body.substring(0,200)" />

            <DisclosurePanel v-else>
                <div v-html="post.body" />
            </DisclosurePanel>
            <div class="flex justify-end">
                <DisclosureButton
                    class="text-blue-500 hover:underline"

                >
                    {{open ? 'Read Less':'Read More'}}
                </DisclosureButton>
            </div>
        </Disclosure>


    </div>

    <div class="grid grid-cols-2 lg:grid-cols-3 gap-3">

        <template  v-for="attachment of post.attachments" :key="attachment.id">
            <div  class="bg-blue-100 group relative text-gray-500  aspect-square flex flex-col items-center justify-center">
<!--Download-->
              <button class="opacity-0 group-hover:opacity-100 transition-all w-8 h-8 text-white bg-gray-500 hover:bg-gray-800 absolute rounded grid place-items-center cursor-pointer right-2 top-2  ">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-w-4 h-4 ">
                      <path fill-rule="evenodd" d="M5.625 1.5H9a3.75 3.75 0 0 1 3.75 3.75v1.875c0 1.036.84 1.875 1.875 1.875H16.5a3.75 3.75 0 0 1 3.75 3.75v7.875c0 1.035-.84 1.875-1.875 1.875H5.625a1.875 1.875 0 0 1-1.875-1.875V3.375c0-1.036.84-1.875 1.875-1.875Zm5.845 17.03a.75.75 0 0 0 1.06 0l3-3a.75.75 0 1 0-1.06-1.06l-1.72 1.72V12a.75.75 0 0 0-1.5 0v4.19l-1.72-1.72a.75.75 0 0 0-1.06 1.06l3 3Z" clip-rule="evenodd" />
                      <path d="M14.25 5.25a5.23 5.23 0 0 0-1.279-3.434 9.768 9.768 0 0 1 6.963 6.963A5.23 5.23 0 0 0 16.5 7.5h-1.875a.375.375 0 0 1-.375-.375V5.25Z" />
                  </svg>
              </button>
<!--                /Download-->
                <img class="w-full  object-cover aspect-square " v-if="isImage(attachment)" :src="attachment.url" :alt="attachment.id">

            <template v-else>
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-16 h-16">
                    <path d="M5.625 1.5c-1.036 0-1.875.84-1.875 1.875v17.25c0 1.035.84 1.875 1.875 1.875h12.75c1.035 0 1.875-.84 1.875-1.875V12.75A3.75 3.75 0 0 0 16.5 9h-1.875a1.875 1.875 0 0 1-1.875-1.875V5.25A3.75 3.75 0 0 0 9 1.5H5.625Z" />
                    <path d="M12.971 1.816A5.23 5.23 0 0 1 14.25 5.25v1.875c0 .207.168.375.375.375H16.5a5.23 5.23 0 0 1 3.434 1.279 9.768 9.768 0 0 0-6.963-6.963Z" />
                </svg>


                <small>{{attachment.name}} </small>
            </template>

            </div>
        </template>
    </div>
    <div class="flex mt-3 flex-row gap-3">
        <button class="flex-1 text-gray-800 flex gap-3 py-2 px-4 justify-center bg-gray-100 rounded hover:bg-gray-200 items-center"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-6">
            <path d="M7.493 18.5c-.425 0-.82-.236-.975-.632A7.48 7.48 0 0 1 6 15.125c0-1.75.599-3.358 1.602-4.634.151-.192.373-.309.6-.397.473-.183.89-.514 1.212-.924a9.042 9.042 0 0 1 2.861-2.4c.723-.384 1.35-.956 1.653-1.715a4.498 4.498 0 0 0 .322-1.672V2.75A.75.75 0 0 1 15 2a2.25 2.25 0 0 1 2.25 2.25c0 1.152-.26 2.243-.723 3.218-.266.558.107 1.282.725 1.282h3.126c1.026 0 1.945.694 2.054 1.715.045.422.068.85.068 1.285a11.95 11.95 0 0 1-2.649 7.521c-.388.482-.987.729-1.605.729H14.23c-.483 0-.964-.078-1.423-.23l-3.114-1.04a4.501 4.501 0 0 0-1.423-.23h-.777ZM2.331 10.727a11.969 11.969 0 0 0-.831 4.398 12 12 0 0 0 .52 3.507C2.28 19.482 3.105 20 3.994 20H4.9c.445 0 .72-.498.523-.898a8.963 8.963 0 0 1-.924-3.977c0-1.708.476-3.305 1.302-4.666.245-.403-.028-.959-.5-.959H4.25c-.832 0-1.612.453-1.918 1.227Z" />
        </svg>
            like
        </button>
        <button class="flex-1 text-gray-800 flex gap-3 py-2 px-4 justify-center bg-gray-100 rounded hover:bg-gray-200 items-center"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-6">
            <path d="M4.913 2.658c2.075-.27 4.19-.408 6.337-.408 2.147 0 4.262.139 6.337.408 1.922.25 3.291 1.861 3.405 3.727a4.403 4.403 0 0 0-1.032-.211 50.89 50.89 0 0 0-8.42 0c-2.358.196-4.04 2.19-4.04 4.434v4.286a4.47 4.47 0 0 0 2.433 3.984L7.28 21.53A.75.75 0 0 1 6 21v-4.03a48.527 48.527 0 0 1-1.087-.128C2.905 16.58 1.5 14.833 1.5 12.862V6.638c0-1.97 1.405-3.718 3.413-3.979Z" />
            <path d="M15.75 7.5c-1.376 0-2.739.057-4.086.169C10.124 7.797 9 9.103 9 10.609v4.285c0 1.507 1.128 2.814 2.67 2.94 1.243.102 2.5.157 3.768.165l2.782 2.781a.75.75 0 0 0 1.28-.53v-2.39l.33-.026c1.542-.125 2.67-1.433 2.67-2.94v-4.286c0-1.505-1.125-2.811-2.664-2.94A49.392 49.392 0 0 0 15.75 7.5Z" />
        </svg>
            comment
        </button>

    </div>


</div>
</template>

<style scoped>

</style>
