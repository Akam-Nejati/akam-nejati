<script setup lang="ts">
const props = defineProps<{
    projects: any
}>()

console.log(props.projects);
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
                        <a :href="item.github" class="text-zinc-900 p-3 rounded-xl bg-green-400 shadow-xl">github</a>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>