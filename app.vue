<script setup lang="ts">
useHead({
  meta:[{
    name: "title",
    content: "Akam Nejati"
  }],
  htmlAttrs: {
    lang: "en"
  }
})
</script>


<template>
  <NuxtLayout>
    <div class="h-screen md:h-[calc(100vh-2rem)] w-full">
      <div class="w-full h-full flex justify-center">
        <div class="main w-full flex flex-col gap-28 px-4 sm:px-20 md:px-4 py-8 overflow-y-scroll !overflow-x-visible">
          <div id="home" class="item w-full block md:hidden">
            <Home />
          </div>
          <div id="skils" class="item">
            <Skils />
          </div>
          <div id="getting-started" class="item">
            <GettingStarted/>
          </div>
          <div id="projects" class="item">
            <Projects />
          </div>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<style>
body {
  @apply bg-zinc-900 text-gray-300 h-screen overflow-hidden
}

.main {
  scroll-behavior: smooth;
}

.main::-webkit-scrollbar {
  width: 0em;
  opacity: 0;
}

.main::-webkit-scrollbar-track {
  opacity: 0;
}

.main::-webkit-scrollbar-thumb {
  opacity: 0;
}
</style>
