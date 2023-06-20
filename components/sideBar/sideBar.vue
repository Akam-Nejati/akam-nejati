<script setup lang="ts">
import thisYear from "~/stores/thisYear"
import SocialMedia from "~/types/socialMedia.interface";
import githubIcon from "~/assets/icons/iconmonstr-github-1.svg"
import telegramIcon from "~/assets/icons/icons8-telegram.svg"


const socialMedias: SocialMedia[] = [
    {
        icon: githubIcon,
        link: "https://github.com/Akam-Nejati"
    },
    {
        icon: telegramIcon,
        link: "https://t.me/Akam_320"
    }
]
</script>

<template>
    <div class="flex justify-between items-top flex-col sm:flex-row md:flex-col md:gap-2 xl:flex-row xl-gap-0">
        <span class="text-2xl xl:text-4xl">Akam Nejati</span>
        <div class="flex flex-col">
            <span class="text-xl text-gray-400 w-full xl:w-[12rem]">Front-end developer _ vue js</span>
        </div>
    </div>
    <div class="w-full h-[20rem] bg-slate-300 rounded-3xl overflow-hidden">
        <img src="~/assets/images/Pixoro-3c3188a68b91c940ae5a4e957548a265.jpg"
            class="w-full h-full object-cover object-center rounded-top" alt="">
    </div>
    <div class="flex flex-col">
        <span class="text-xl xl:text-3xl">mr.akam.320@gmail.com</span>
        <span class="text-xl xl:text-3xl mt-4">Iran - Mahabad</span>
        <span class="text-xl xl:text-3xl mt-4">born in 2006</span>
    </div>
    <div class="">
        <p class="text-sm xl:text-xl text-center text-gray-400">© {{ thisYear }} Akam All Rights Reserved</p>
    </div>
    <div class="flex justify-center gap-6">
        <div v-for="(socialMedia, index) in socialMedias" :key="index" class="xl:w-20 xl:h-20 rounded-full border">
            <a :href="socialMedia.link" class="w-full h-full flex justify-center items-center">
                <img class="w-10 icon-color" :src="socialMedia.icon" alt="">
            </a>
        </div>
    </div>
    <a class="w-full py-3 md:py-2 xl:py-3 rounded-full bg-green-400 text-zinc-900 text-xl flex justify-center items-center"
        href="https://t.me/Akam_320">
        <Icon name="line-md:email-twotone" class="text-2xl mr-2" />
        <span class="md:text-sm xl:text-xl">
            SEND MASSAGE
        </span>
    </a>
</template>


<style>
.icon-color {
    filter: invert(93%) sepia(15%) saturate(83%) hue-rotate(177deg) brightness(89%) contrast(95%);
}
</style>