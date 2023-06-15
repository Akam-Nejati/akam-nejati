<template>
    <div class="flex justify-between gap-4">
        <div class="p-8 md:w-[24rem] xl:w-[30rem] rounded-3xl border border-zinc-800 shadow-xl h-[calc(100vh-2rem)] flex flex-col justify-between">
            <SideBar />
        </div>
        <div class="md:w-[calc(95%-25rem)] xl:w-[calc(95%-31rem)]">
            <slot />
        </div>
        <div class="w-[5%] py-8 ">
            <Menu />
        </div>
    </div>
</template>
