<template>
  <section class="py-20">
    <div class="container mx-auto max-w-6xl px-4">
      
      <!-- Section Header -->
      <div class="text-center mb-16 space-y-4">
        <div class="inline-block px-4 py-1.5 bg-primary/10 rounded-full mb-4">
          <span class="text-sm font-medium text-primary">Our Services</span>
        </div>
        <h2 class="text-4xl md:text-5xl font-bold tracking-tight">
          Services We Provide
        </h2>
        <p class="text-muted-foreground max-w-2xl mx-auto text-lg">
          Professional web solutions tailored to your business needs.
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        
        <!-- Web Design -->
        <Card class="group hover:shadow-xl transition-all duration-300 hover:-translate-y-2 border-2 hover:border-primary/50">
          <CardHeader class="space-y-4">
            <div class="w-14 h-14 bg-linear-to-br from-primary to-secondary rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold group-hover:text-primary transition-colors">
              Web Design
            </h3>
          </CardHeader>
          <CardContent>
            <p class="text-muted-foreground leading-relaxed">
              Custom website design focused on performance, usability, and modern UI standards.
            </p>
          </CardContent>
        </Card>

        <!-- Website Redesign -->
        <Card class="group hover:shadow-xl transition-all duration-300 hover:-translate-y-2 border-2 hover:border-primary/50">
          <CardHeader class="space-y-4">
            <div class="w-14 h-14 bg-linear-to-br from-secondary to-primary rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold group-hover:text-primary transition-colors">
              Website Redesign
            </h3>
          </CardHeader>
          <CardContent>
            <p class="text-muted-foreground leading-relaxed">
              Revamping existing websites to improve user experience, speed, and visual identity.
            </p>
          </CardContent>
        </Card>

        <!-- Hosting Services -->
        <Card class="group hover:shadow-xl transition-all duration-300 hover:-translate-y-2 border-2 hover:border-primary/50">
          <CardHeader class="space-y-4">
            <div class="w-14 h-14 bg-linear-to-br from-primary to-secondary rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold group-hover:text-primary transition-colors">
              Web Hosting
            </h3>
          </CardHeader>
          <CardContent>
            <p class="text-muted-foreground leading-relaxed">
              Secure, reliable, and scalable hosting solutions for modern web applications.
            </p>
          </CardContent>
        </Card>

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Card, CardHeader, CardContent } from '@/components/ui/card'
</script>