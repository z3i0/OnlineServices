<script setup lang='ts'>
import NavBar from "./ui/NavBar.vue"
import Footer from "./ui/Footer.vue"
defineProps<{
  msg: string
}>()
</script>

<template>
  <NavBar />
  <main class="flex justify-center p-10">
    <p class="text-3xl font-bold underline">
      {{ msg }}
    </p>
  </main>
  <Footer />
</template>