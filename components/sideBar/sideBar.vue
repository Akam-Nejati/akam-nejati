<script setup lang="ts">
const { data: userInformation }: { data: Ref<any> } = await useFetch("http://localhost:1337/api/sidebar?populate[0]=photo&populate[1]=socialMedias.icon")
const { City, email, additionalWork, photo, socialMedias } = userInformation.value.data.attributes
</script>

<template>
    <div class="flex justify-between items-top md:flex-col md:gap-2 xl:flex-row xl-gap-0">
        <span class="md:text-2xl xl:text-4xl">Akam Nejati</span>
        <div class="flex flex-col">
            <span class="text-xl md:w-full xl:w-[12rem]">{{ additionalWork }}</span>
        </div>
    </div>
    <div class="w-full h-[20rem] bg-slate-300 rounded-3xl overflow-hidden">
        <img :src="`http://localhost:1337${photo.data.attributes.url}`"
            class="w-full h-full object-cover object-top rounded-top" alt="">
    </div>
    <div class="flex flex-col">
        <span class="md:text-xl xl:text-3xl">{{ email }}</span>
        <span class="md:text-xl xl:text-3xl mt-4">{{ City }}</span>
        <span class="md:text-xl xl:text-3xl mt-4">born in 2006</span>
    </div>
    <div class="">
        <p class="md:text-sm xl:text-xl text-center text-gray-400">© 2023 Akam All Rights Reserved</p>
    </div>
    <div class="flex justify-center gap-6">
        <div v-for="socialMedia in socialMedias" class="xl:w-20 xl:h-20 rounded-full border">
            <a :href="socialMedia.link" class="w-full h-full flex justify-center items-center">
                <img class="w-10 icon-color" :src="`http://localhost:1337${socialMedia.icon.data.attributes.url}`" alt="">
            </a>
        </div>
    </div>
    <a class="w-full md:py-2 xl:py-3 rounded-full bg-green-400 text-zinc-900 text-xl flex justify-center items-center"
        href="https://t.me/Akam_320">
        <Icon name="line-md:email-twotone" class="text-2xl mr-2" />
        <span class="md:text-sm xl:text-xl">
            HIRE ME!
        </span>
    </a>
</template>


<style>
.icon-color {
    filter: invert(93%) sepia(15%) saturate(83%) hue-rotate(177deg) brightness(89%) contrast(95%);
}
</style>