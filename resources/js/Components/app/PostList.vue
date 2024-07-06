<script setup>

import PostItem from "@/Components/app/PostItem.vue";

const post1 = {
    user: {
        id: 1,
        avatar:"https://randomuser.me/api/portraits/lego/4.jpg",
        name: "Kelvin Githu"
    },
    group: null,
    attachments:[
        {
             id:3,
            name:"test3.png",
            mime:"image/png",
            url:"https://picsum.photos/1000",
        },
        {
            id:5 ,
            name:"welcome3.pdf",
            mime:"image/png",
            url:"https://picsum.photos/1000",
        }
    ],
    body: `<p>Pork shoulder pie has to have a sour, sliced lentils component.
Cook meatloaf regularly sour, then mix with condensed milk and serve smoothly in saucepan.
Cook niffy rhubarbs in a cooker with triple sec for about an hour to increase their sweetness.
Squeezed cabbage can be made al dente by mixing with honey.</p>

<p>
The moon is more teleporter now than particle.
solid and rudely collective.This mankind has only been
transfered by a sub-light planet.Dozens of deaths will be
lost in alarms like peaces in futures
</p>


`,
    created_at: "2024-05-12 15:12"

}

const post2 = {
    user: {
        id: 2,
        avatar:"https://randomuser.me/api/portraits/lego/3.jpg",
        name: "John Doe"
    },
    group: {
        id:1,
        name:"Vue.Js Developers"
    },
    attachments:[
        {id:1,
        name:"test.png",
        mime:"image/png",
        url:"https://picsum.photos/1000",},
        {id:2,
        name:"welcome.pdf",
        mime:"application/pdf",
        url:"#",}
    ],
    body: `<p>Pork shoulder pie has to have a sour, sliced lentils component.
Cook meatloaf regularly sour, then mix with condensed milk and serve smoothly in saucepan.
Cook niffy rhubarbs in a cooker with triple sec for about an hour to increase their sweetness.
Squeezed cabbage can be made al dente by mixing with honey.</p>

<p>
The moon is more teleporter now than particle.
solid and rudely collective.This mankind has only been
transfered by a sub-light planet.Dozens of deaths will be
lost in alarms like peaces in futures
</p>


`,
    created_at: "2024-04-12 15:12"

}

</script>

<template>
    <div class="flex h-full overflow-auto flex-col gap-4">
        <PostItem :post="post1"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
        <PostItem :post="post2"/>
    </div>
</template>
