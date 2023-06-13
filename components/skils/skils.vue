<template>
    <div class="w-[8rem] px-4 py-1 border border-gray-300 rounded-full flex justify-between items-center shadow-xl">
        <div>
            <Icon name="bxs:shapes" class="text-xl" />
        </div>
        <span class="text-gray-300 ml-2">My skils</span>
    </div>
    <div class="grid grid-cols-6 mt-8 gap-5">
        <div v-for="(skil, index) in skils" :key="index" class="col-span-1 p-8 rounded-xl border border-zinc-800 shadow-xl flex flex-col justify-between">
            <img class="w-full" :src="`http://localhost:1337${skil.logo.data.attributes.url}`" :alt="skil.name">
            <span class="text-xl mt-4 flex justify-center">{{ skil.name }}</span>
        </div>
    </div>
</template>

<script setup lang="ts">
const props = defineProps<{
    skils: any
}>()
</script>

<style>
.typed-cursor::after {
    content: "_";
    margin-left: 2px;
    font-size: 3rem;
    color: #4ADE80;
}
</style>