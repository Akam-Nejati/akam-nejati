<script setup lang="ts">
const props = defineProps<{
    skils: any
}>()
</script>

<template>
    <div class="w-[8rem] px-4 py-1 border border-gray-300 rounded-full flex justify-between items-center shadow-xl">
        <div>
            <Icon name="bxs:shapes" class="text-xl" />
        </div>
        <span class="text-gray-300 ml-2">My skils</span>
    </div>
    <div class="grid md:grid-cols-4 lg:grid-cols-6 xl:grid-cols-5 mt-8 gap-5">
        <div v-for="(skil, index) in skils" :key="index"
            class="col-span-2 xl:col-span-1 p-8 rounded-xl border border-zinc-800 shadow-xl flex flex-col justify-between">
            <div class="flex justify-center">
                <img class="w-20 h-16" :src="`http://localhost:1337${skil.logo.data.attributes.url}`" :alt="skil.name">
            </div>
            <span class="text-xl mt-4 flex justify-center">{{ skil.name }}</span>
        </div>
    </div>
</template>


<style>
.typed-cursor::after {
    content: "_";
    margin-left: 2px;
    font-size: 3rem;
    color: #4ADE80;
}
</style>