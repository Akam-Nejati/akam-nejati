<template>
    <div class="flex justify-between">
        <div class="p-8 w-[30rem] rounded-3xl border border-zinc-800 shadow-xl h-[calc(100vh-2rem)] flex flex-col justify-between mr-4">
            <div class="flex justify-between items-top">
                <span class="text-4xl">Akam Nejati</span>
                <div class="flex flex-col">
                    <span class="text-xl w-[12rem]">{{ additionalWork }}</span>
                </div>
            </div>
            <div class="w-full h-[20rem] bg-slate-300 rounded-3xl overflow-hidden">
                <img :src="`http://localhost:1337${photo.data.attributes.url}`" class="w-full h-full object-cover object-top rounded-top" alt="">
            </div>
            <div class="flex flex-col">
                <span class="text-3xl">{{ email }}</span>
                <span class="text-3xl mt-4">{{ City }}</span>
                <span class="text-3xl mt-4">born in 2006</span>
            </div>
            <div class="">
                <p class="text-xl text-center text-gray-400">© 2023 Akam All Rights Reserved</p>
            </div>
            <div class="flex justify-center gap-6">
                <div v-for="socialMedia in socialMedias" class="w-20 h-20 rounded-full border">
                    <a :href="socialMedia.link" class="w-full h-full flex justify-center items-center">
                        <img class="w-10 icon-color" :src="`http://localhost:1337${socialMedia.icon.data.attributes.url}`" alt="">
                    </a>
                </div>
            </div>
            <a class="w-full py-3 rounded-full bg-green-400 text-zinc-900 text-xl flex justify-center items-center" href="https://t.me/Akam_320">
                <Icon name="line-md:email-twotone" class="text-2xl mr-2"/>
                <span>
                    HIRE ME!
                </span>
            </a>
        </div>
        <div class="w-[calc(100%-31rem)]">
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">
const { data: userInformation }: { data: Ref<any> } = await useFetch("http://localhost:1337/api/sidebar?populate[0]=photo&populate[1]=socialMedias.icon")

const { City, email, additionalWork, photo, socialMedias } = userInformation.value.data.attributes
</script>

<style>
    .icon-color{
        filter: invert(93%) sepia(15%) saturate(83%) hue-rotate(177deg) brightness(89%) contrast(95%);
    }
</style>