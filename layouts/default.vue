<template>
    <div>
        <div class="p-8 w-[27rem] rounded-3xl border border-zinc-600 h-[calc(100vh-2rem)] flex flex-col justify-between">
            <div class="flex justify-between items-center">
                <span class="text-5xl">Akam Nejati</span>
                <div class="flex flex-col">
                    <span class="text-xl w-[9rem]">{{ additionalWork }}</span>
                </div>
            </div>
            <div class="w-full h-[20rem] bg-slate-300 rounded-3xl">
                <img :src="`http://localhost:1337${photo.data.attributes.url}`" class="w-full h-full object-cover object-top rounded-top" alt="">
            </div>
            <div class="flex flex-col">
                <span class="text-3xl">{{ email }}</span>
                <span class="text-3xl mt-4">{{ City }}</span>
            </div>
            <div class="">
                <p class="text-xl text-center text-gray-400">© 2023 Akam All Rights Reserved</p>
            </div>
            <div class="flex justify-between">
                <div class="w-20 h-20 rounded-full border">
                </div>
            </div>
            <button class="w-full py-3 rounded-full bg-green-400 text-zinc-900 text-xl">HIRE ME!</button>
        </div>
        <div>
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">
const { data: userInformation }: { data: Ref<any> } = await useFetch("http://localhost:1337/api/sidebar?populate=*")

const { City, email, additionalWork, photo } = userInformation.value.data.attributes
</script>