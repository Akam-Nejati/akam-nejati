<script setup lang="ts">
import thisYear from "~/stores/thisYear"
import GettingStartedPoint from "~/types/gettingStartedPoint.interface";

const gettingStarted: GettingStartedPoint[] = [
    {
        date: "2019",
        discription: "Start of activity in the field of front end"
    },
    {
        date: "2021",
        discription: "Start learning vue js",
    },
    {
        date: "2023",
        discription: "Start learning nuxt js",
    }
]
</script>

<template>
    <Label icon_name="gis:flag-start-b" title="Getting started"/>

    <div class="mt-8">
        <div class="flex flex-col-reverse px-3">
            <div v-for="(item, index) in gettingStarted" :key="index" class="border-l-2 relative" :class="{'border-green-400': +item.date === thisYear}">
                <div class="flex flex-col justify-between gap-3 ml-8 pb-8 after:w-5 after:h-5 after:bg-gray-300 after:absolute after:top-0 after:left-[-.7rem] after:rounded-full" :class="{ 'after:bg-green-400': +item.date === thisYear }" >
                    <span class="text-xl xl:text-3xl">{{ item.date }}</span>
                    <span class="text-xl xl:text-3xl text-gray-400">{{ item.discription }}</span>
                </div>
            </div>
        </div>
    </div>
</template>
