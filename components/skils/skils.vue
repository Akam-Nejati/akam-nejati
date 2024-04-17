<script setup lang="ts">
import type Skil from '~/types/skil.interface';
import htmlIcon from "~/assets/icons/html-1.svg"
import cssIcon from "~/assets/icons/w3_css-icon.svg"
import scssIcon from "~/assets/icons/Sass_Logo_Color.svg"
import bootstrapIcon from "~/assets/icons/bootstrap-svgrepo-com.svg"
import tailwindIcon from "~/assets/icons/Tailwind_CSS_Logo.svg"
import jsIcon from "~/assets/icons/Unofficial_JavaScript_logo_2.svg"
import tsIcon from "~/assets/icons/Typescript.svg"
import vuejsIcon from "~/assets/icons/Vue.js_Logo_2.svg"
import quasarIcon from "~/assets/icons/quasar-svgrepo-com 1.svg"
import vuetifyIcon from "~/assets/icons/vuetify.svg"
import piniaIcon from "~/assets/icons/pinia-seeklogo.com.svg"
import nuxtIcon from "~/assets/icons/nuxt-2.svg"
import gitIcon from "~/assets/icons/git-icon-logo-svgrepo-com.svg"
import githubIcon from "~/assets/icons/iconmonstr-github-1.svg"

const skils: Skil[] = [
    {
        name: "Html",
        icon: htmlIcon
    },
    {
        name: "Css",
        icon: cssIcon
    },
    {
        name: "Scss",
        icon: scssIcon
    },
    {
        name: "Bootstrap",
        icon: bootstrapIcon
    },
    {
        name: "Tailwind",
        icon: tailwindIcon
    },
    {
        name: "Js",
        icon: jsIcon
    },
    {
        name: "ts",
        icon: tsIcon
    },
    {
        name: "Vue js",
        icon: vuejsIcon
    },
    {
        name: "Quasar",
        icon: quasarIcon
    },
    {
        name: "Vuetify",
        icon: vuetifyIcon
    },
    {
        name: "Pinia",
        icon: piniaIcon
    },
    {
        name: "Nuxt js",
        icon: nuxtIcon
    },
    {
        name: "Git",
        icon: gitIcon
    },
    {
        name: "Github",
        icon: githubIcon
    },
]
</script>

<template>
    <Label icon_name="bxs:shapes" title="My skils"/>
    <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 xl:grid-cols-5 mt-8 gap-3 md:gap-5">
        <div v-for="(skil, index) in skils" :key="index"
            class="col-span-1 md:col-span-2 xl:col-span-1 p-8 rounded-xl border border-zinc-800 shadow-xl flex flex-col justify-between">
            <div class="flex justify-center">
                <img class="w-20 h-16" :src="skil.icon" :alt="skil.name">
            </div>
            <span class="text-xl mt-4 flex justify-center">{{ skil.name }}</span>
        </div>
    </div>
</template>