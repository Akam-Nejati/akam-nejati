<script setup lang="ts">
defineProps<{
    icon_name: string,
    title: string,
}>()
</script>

<template>
    <div class="px-4 py-1 border border-gray-300 rounded-full inline-block shadow-xl">
        <div class="flex justify-center items-center gap-4">
            <div>
                <Icon :name="icon_name" class="text-lg xl:text-xl" />
            </div>
            <span class="text-lg xl:text-xl text-gray-300 ml-2">{{ title }}</span>
        </div>
    </div>
</template>
