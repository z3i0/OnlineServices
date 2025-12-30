<script setup lang='ts'>
import NavBar from "./ui/NavBar.vue"
import Footer from "./ui/Footer.vue"
import Hero from "./ui/Hero.vue"
import ServicesSection from "./ui/ServicesSection.vue";
defineProps<{
  msg: string
}>()
</script>

<template>
  <main >
    <NavBar />
    <Hero />
    <ServicesSection />
    <Footer />
  </main>
</template>