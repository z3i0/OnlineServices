<script setup lang='ts'>
import NavBar from "./ui/NavBar.vue"
import Footer from "./ui/Footer.vue"
import Hero from "./ui/Hero.vue"
import ServicesSection from "./ui/ServicesSection.vue";
import WhyChooseUs from "./ui/WhyChooseUs.vue";
import WhyWeStarted from "./ui/WhyWeStarted.vue";
defineProps<{
  msg: string
}>()
</script>

<template>
  <main>
    <NavBar />
    <Hero />
    <ServicesSection />
    <WhyChooseUs />
    <WhyWeStarted />
    <Footer />
  </main>
</template>