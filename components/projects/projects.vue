<script setup lang="ts">
import type Project from '~/types/project.interface';

const projects: Project[] = [
    {
        openSorce: false,
        title: "Petro engine",
        discription: "a shoping website like Divar. (website and dashboard, for admin and users)",
        preview: "https://code-converter-ai.vercel.app/",
        github: "https://petro-engine.vercel.app"
    },
    {
        openSorce: false,
        title: "boomilia",
        discription: "a architecture web site like Pintrest. (nuxt3)",
        preview: "https://code-converter-ai.vercel.app/",
        github: "https://boomilia.com"
    },
    {
        title: "Qwitter",
        discription: "a small app same to twitter with vue js and vuetify",
        preview: "https://qwitter.iran.liara.run/home",
        github: "https://github.com/Akam-Nejati/qwitter"
    },
    {
        title: "Dashboard",
        discription: "a simple admin dashboard using vue and primevue",
        preview: "https://dashboard-swart-kappa.vercel.app/",
        github: "https://github.com/Akam-Nejati/dashboard"
    },
    {
        title: "Code converter ai",
        discription: "an app to convert code with chat gpt, vue js and tailwind css",
        preview: "https://code-converter-ai.vercel.app/",
        github: "https://github.com/Akam-Nejati/code-converter-ai"
    },
]
</script>

<template>
    <Label icon_name="arcticons:zoho-projects" title="Projects" />
    <div class="grid grid-cols-2 xl:grid-cols-3 mt-8 gap-4">
        <div v-for="(item, index) in projects" :key="index"
            class="col-span-2 lg:col-span-1 xl:col-span-1 relative rounded-3xl overflow-hidden cursor-pointer border border-zinc-800 shadow-xl">
            <div class="h-full p-8">
                <div class="h-full flex flex-col justify-between items-center gap-4">
                    <div class="flex flex-col justify-between items-center">
                        <span class="text-xl font-bold text-gray-300">
                            {{ item.title }}
                        </span>
                        <p class="mt-4 text-lg p-4">
                            {{ item.discription }}
                        </p>
                    </div>

                    <div class="flex gap-4">
                        <a :href="item.preview" class="text-zinc-900 p-3 rounded-xl bg-gray-300 shadow-xl">preview</a>
                        <a :href="item.github" class="text-zinc-900 p-3 rounded-xl bg-green-400 shadow-xl" v-if="item.openSorce !== false">github</a>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>