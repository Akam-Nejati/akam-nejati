<template>
    <div class="flex justify-around xl:justify-between">
        <div class="p-8 m-4 sm:w-[24rem] xl:w-[30rem] rounded-3xl border border-zinc-800 shadow-xl h-[calc(100vh-2rem)] hidden md:flex flex-col justify-between gap-4">
            <SideBar />
        </div>
        <div class="w-full md:w-[calc(100%-25rem)] xl:w-[calc(100%-31rem)]">
            <slot />
        </div>
    </div>
</template>
