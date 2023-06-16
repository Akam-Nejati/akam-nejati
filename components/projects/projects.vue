<script setup lang="ts">
const props = defineProps<{
    projects: any
}>()

console.log(props.projects);
</script>

<template>
    <div class="w-[8rem] px-4 py-1 border border-gray-300 rounded-full flex justify-between items-center shadow-xl">
        <div>
            <Icon name="arcticons:zoho-projects" class="text-xl" />
        </div>
        <span class="text-gray-300 ml-2">projects</span>
    </div>
    <div class="grid grid-cols-2 mt-4 gap-4">
        <div v-for="(item, index) in projects" :key="index"
            class="col-span-2 lg:col-span-1 relative rounded-3xl overflow-hidden cursor-pointer h-[15rem] border border-zinc-800 shadow-xl">

            <img :src="item.photo.data.attributes.url" :alt="item.title" class="brightness-75 w-full h-full object-cover">

            <div class="information w-full h-full absolute top-0 left-0 bg-zinc-900 bg-opacity-80">
                <div class="h-full p-8">
                    <div class="h-full flex flex-col justify-between items-center">
                        <div class="flex flex-col justify-between items-center">
                            <span class="text-xl font-bold text-gray-300">
                                {{ item.title }}
                            </span>
                            <p class="mt-4 text-lg">
                                {{ item.discription }}
                            </p>
                        </div>

                        <div class="flex gap-4">
                            <a :href="item.preview" class="text-zinc-900 p-3 rounded-xl bg-gray-300 shadow-xl">preview</a>
                            <a :href="item.github" class="text-zinc-900 p-3 rounded-xl bg-green-400 shadow-xl">github</a>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>