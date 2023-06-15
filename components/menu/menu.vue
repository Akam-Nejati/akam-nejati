<script setup lang="ts">
import MenuItem from "~/types/menuItem.interface"

const showMenu = useState<boolean>(() => true)
const menuItems: MenuItem[] = [
    {
        icon: "bxs:shapes",
        link: "skils"
    },
    {
        icon: "gis:flag-start-b",
        link: "getting-started"
    },
    {
        icon: "bxs:shapes",
        link: "skils"
    },
    {
        icon: "bxs:shapes",
        link: "skils"
    },
]
</script>

<template>
    <div @click="showMenu = !showMenu" class="px-4 py-3 rounded-full bg-green-400 inline-block cursor-pointer shadow-xl">
        <Icon name="pepicons-pop:menu" class="text-xl text-zinc-900" />
    </div>
    <div class="h-[calc(100vh-8rem)] flex items-center">
        <Transition>
            <div v-if="showMenu" class="rounded-full border border-zinc-800 shadow-xl inline-block">
                <div class="w-full h-full flex flex-col justify-between gap-4">
                    <div v-for="(item, index) in menuItems" :key="index" class="px-4 py-3 cursor-pointer">
                        <a href="#skils">
                            <Icon :name="item.icon" class="text-xl text-gray-400" />
                        </a>
                    </div>
                </div>
            </div>
        </Transition>
    </div>
</template>


<style>
.v-enter-active,
.v-leave-active {
    transition: all 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    transform: translateX(65px);
    opacity: 0;
}
</style>