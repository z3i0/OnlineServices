<script setup lang="ts">
import { Layout, RefreshCw, Server, ArrowRight } from 'lucide-vue-next'
import { Card, CardHeader, CardContent } from '@/components/ui/card'
import { Button } from '@/components/ui/button'

const services = [
  {
    title: 'Web Design',
    description: 'Custom website design focused on performance, usability, and modern UI standards.',
    icon: Layout,
    gradient: 'from-primary to-secondary'
  },
  {
    title: 'Website Redesign',
    description: 'Revamping existing websites to improve user experience, speed, and visual identity.',
    icon: RefreshCw,
    gradient: 'from-secondary to-primary'
  },
  {
    title: 'Web Hosting',
    description: 'Secure, reliable, and scalable hosting solutions for modern web applications.',
    icon: Server,
    gradient: 'from-primary to-accent'
  }
]
</script>

<template>
  <section class="py-24 relative overflow-hidden">
    <!-- Background decorations -->
    <div class="absolute top-0 right-0 w-1/3 h-1/3 bg-primary/5 rounded-full blur-3xl -z-10"></div>
    <div class="absolute bottom-0 left-0 w-1/3 h-1/3 bg-secondary/5 rounded-full blur-3xl -z-10"></div>

    <div class="container mx-auto max-w-7xl px-4">

      <!-- Section Header -->
      <div class="text-center mb-16 space-y-6">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-primary/10 rounded-full mb-4 border border-primary/20">
          <span class="w-2 h-2 rounded-full bg-primary animate-pulse"></span>
          <span class="text-sm font-semibold text-primary tracking-wide">Our Expertise</span>
        </div>
        <h2 class="text-4xl md:text-5xl font-black tracking-tight text-foreground leading-tight">
          Services We <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Provide</span>
        </h2>
        <p class="text-muted-foreground max-w-2xl mx-auto text-lg leading-relaxed">
          Professional web solutions tailored to your business needs, built with cutting-edge technology.
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        <Card v-for="(service, index) in services" :key="index"
          class="group relative overflow-hidden border-primary/10 bg-card/40 backdrop-blur-sm hover:shadow-2xl hover:shadow-primary/5 hover:-translate-y-1 transition-all duration-300">

          <!-- Gradient Hover Effect -->
          <div
            class="absolute inset-0 bg-gradient-to-br opacity-0 group-hover:opacity-10 transition-opacity duration-500"
            :class="[service.gradient]">
          </div>

          <CardHeader class="relative z-10 pb-4">
            <div
              class="w-14 h-14 rounded-2xl bg-gradient-to-br flex items-center justify-center mb-6 shadow-lg transform group-hover:scale-110 transition-transform duration-300"
              :class="[service.gradient]">
              <component :is="service.icon" class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-2xl font-bold text-foreground group-hover:text-primary transition-colors duration-300">
              {{ service.title }}
            </h3>
          </CardHeader>

          <CardContent class="relative z-10 space-y-6">
            <p class="text-muted-foreground leading-relaxed text-lg">
              {{ service.description }}
            </p>

            <div class="pt-2">
              <Button variant="link" class="p-0 h-auto text-primary font-semibold group/btn">
                Learn more
                <ArrowRight class="w-4 h-4 ml-1 group-hover/btn:translate-x-1 transition-transform" />
              </Button>
            </div>
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>