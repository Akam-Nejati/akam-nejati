<template>
    <div class="container h-[calc(100vh-2rem)] overflow-y-scroll">
        <div v-for="item in 4" class="item w-full h-full bg-slate-300 my-4 flex justify-center items-center">
            <span class="text-5xl text-zinc-900">
                {{ item }}
            </span>
        </div>
    </div>
</template>


<style>
    .container{
        scroll-snap-type: y mandatory;
    }

    .item{
        scroll-snap-align: center;
    }
</style>