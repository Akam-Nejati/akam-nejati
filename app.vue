<template>
  <NuxtLayout>
    <div class="container h-[calc(100vh-2rem)] overflow-y-scroll">
      <div class="h-full flex justify-center">
        <div class="w-[60rem] p-8">
          <Skils :skils="skils"/>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<style>
body {
  @apply bg-zinc-900 text-gray-300 p-4 h-screen
}
</style>

<script setup lang="ts">
const { data: content }: { data: Ref<any> } = await useFetch("http://localhost:1337/api/content?populate[0]=*&populate[1]=skils&populate[2]=skils.logo")
const { skils } = content.value.data.attributes

console.log(skils);

</script>