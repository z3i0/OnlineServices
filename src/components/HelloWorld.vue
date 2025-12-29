<script setup lang='ts'>
import NavBar from "./ui/NavBar.vue"
import Footer from "./ui/Footer.vue"
import Hero from "./ui/Hero.vue"
defineProps<{
  msg: string
}>()
</script>

<template>
  <main >
    <NavBar />
    <Hero />
  </main>
  <Footer />
</template>