<script setup lang="ts">
const { data: content }: { data: Ref<any> } = await useFetch("http://localhost:1337/api/content", {
  params: {
    "populate[0]": "*",
    "populate[1]": "skils",
    "populate[2]": "skils.logo",
    "populate[3]": "gettingStarted",
    "populate[4]": "projects",
    "populate[5]": "projects.photo",
  }
})

const { skils, gettingStarted, projects } = content.value.data.attributes
</script>

<template>
  <NuxtLayout>
    <div class="h-[calc(100vh-2rem)]">
      <div class="h-full flex justify-center">
        <div class="container flex flex-col gap-28 w-[60rem] py-8 overflow-y-scroll !overflow-x-visible">
          <div id="home" class="item block xl:hidden">
            <Home />
          </div>
          <div id="skils" class="item">
            <Skils :skils="skils" />
          </div>
          <div id="getting-started" class="item">
            <GettingStarted :gettingStarted="gettingStarted" />
          </div>
          <div id="projects" class="item">
            <Projects :projects="projects" />
          </div>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<style>
body {
  @apply bg-zinc-900 text-gray-300 p-4 h-screen overflow-hidden
}

/* .container {
  scroll-snap-type: y mandatory;
}
 */
/* .item {
  scroll-margin: 0;
} */

.container {
  scroll-behavior: smooth;
}

.container::-webkit-scrollbar {
  width: 0em;
  opacity: 0;
}

.container::-webkit-scrollbar-track {
  opacity: 0;
}

.container::-webkit-scrollbar-thumb {
  opacity: 0;
}
</style>
