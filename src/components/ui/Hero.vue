<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'
import { ArrowRight } from 'lucide-vue-next';

const handleBookMeeting = () => {
  console.log('Getting started...')
  // Add your logic here
}

const handleLearnMore = () => {
  console.log('Learning more...')
  // Add your logic here
}
</script>
<template>
  <div>
    <!-- Main Content Container -->
    <div class="min-h-screen relative z-10 container mx-auto px-4 sm:px-6 lg:px-8 max-w-7xl">
      <div class="flex items-center">
        <div class="grid lg:grid-cols-2 gap-16 items-center w-full py-12">
          <!-- Left Content Section -->
          <div class="space-y-10 max-w-2xl">
            <!-- Badge -->
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full border border-primary/20 bg-primary/5">
              <div class="w-2 h-2 rounded-full bg-primary animate-pulse"></div>
              <span class="text-sm font-medium text-primary">Conri Coding</span>
            </div>

            <!-- Main Heading -->
            <div class="space-y-6">
              <h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold leading-tight text-foreground">
                Transforming Data
                into 
                <span class="relative inline-block">
                  <span class="relative z-10 text-primary">
                    Decisions
                  </span>
                  <span class="absolute inset-0 bg-primary/10 rounded-xl transform -rotate-1"></span>
                </span>
              </h1>
              
              <p class="text-lg sm:text-xl leading-relaxed max-w-xl text-muted-foreground">
                Leverage the power of machine learning and AI to unlock insights and drive business growth with cutting-edge technology
              </p>
            </div>

            <!-- CTA Section -->
            <div class="flex flex-col sm:flex-row gap-4">
              <Button 
                class="group px-8 py-6 text-base font-semibold rounded-xl bg-primary text-primary-foreground shadow-lg hover:shadow-xl transition-all duration-300 hover:scale-105"
                @click="handleBookMeeting"
              >
                Get Started
                <ArrowRight class="w-5 h-5 transition-transform group-hover:translate-x-1" />
              </Button>
              
              <Button 
                class="px-8 py-6 text-base font-semibold rounded-xl border-2 border-primary/30 text-primary bg-transparent transition-all duration-300 hover:scale-105 hover:bg-primary/5"
                @click="handleLearnMore"
              >
                Learn More
              </Button>
            </div>

            <!-- Social Proof -->
            <div class="flex flex-wrap items-center gap-6 pt-4">
              <div class="flex -space-x-3">
                <Avatar 
                  v-for="seed in ['Felix', 'Aneka', 'Sarah', 'Bob']" 
                  :key="seed"
                  class="w-12 h-12 ring-4 ring-background border-2 border-border"
                >
                  <AvatarImage :src="`https://api.dicebear.com/7.x/avataaars/svg?seed=${seed}`" />
                  <AvatarFallback class="bg-primary/10 text-primary font-semibold">
                    {{ seed[0] }}
                  </AvatarFallback>
                </Avatar>
              </div>
              
              <div class="flex flex-col">
                <div class="flex items-center gap-1">
                  <svg v-for="i in 5" :key="i" class="w-4 h-4 text-accent" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/>
                  </svg>
                </div>
                <p class="text-sm font-medium text-muted-foreground">
                  Trusted by <span class="text-primary font-bold">100+</span> leading companies
                </p>
              </div>
            </div>
          </div>

          <!-- Right Content - Illustration -->
          <div class="relative lg:scale-110">
            <!-- Floating card decorations -->
            <!-- <div class="absolute -top-8 -left-8 p-4 rounded-2xl shadow-2xl animate-float bg-card border border-border">
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-xl flex items-center justify-center bg-secondary/15">
                  <svg class="w-6 h-6 text-secondary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                          d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
                  </svg>
                </div>
                <div>
                  <p class="text-xs font-semibold text-muted-foreground">Analytics</p>
                  <p class="text-lg font-bold text-foreground">+24.5%</p>
                </div>
              </div>
            </div> -->

            <!-- <div class="absolute -bottom-8 -right-8 p-4 rounded-2xl shadow-2xl animate-float delay-1500 bg-card border border-border">
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-xl flex items-center justify-center bg-accent/15">
                  <svg class="w-6 h-6 text-accent" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                          d="M13 10V3L4 14h7v7l9-11h-7z"/>
                  </svg>
                </div>
                <div>
                  <p class="text-xs font-semibold text-muted-foreground">Performance</p>
                  <p class="text-lg font-bold text-foreground">Fast</p>
                </div>
              </div>
            </div> -->

            <!-- <div class="absolute top-1/2 -left-12 p-3 rounded-xl shadow-xl animate-float delay-500 bg-card border border-border">
              <div class="w-10 h-10 rounded-lg flex items-center justify-center bg-primary/15">
                <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6V4m0 2a2 2 0 100 4m0-4a2 2 0 110 4m-6 8a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4m6 6v10m6-2a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4"/>
                </svg>
              </div>
            </div> -->

            <!-- Main illustration container -->
            <div class="hidden sm:block relative rounded-3xl p-12 backdrop-blur-sm border border-border bg-gradient-to-br from-primary/[0.03] to-secondary/[0.03]">
              <!-- Glow effect -->
              <div class="absolute inset-0 rounded-3xl blur-3xl -z-10 bg-gradient-to-br from-primary/15 to-secondary/15"></div>
              
              <!-- Image container -->
              <div class="relative">
                <img 
                  src="../../assets/logo.png" 
                  alt="Logo" 
                  class="w-full h-auto drop-shadow-2xl animate-float-slow"
                />

                <!-- Orbital rings -->
                <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
                  <div class="absolute w-full h-full border border-primary/10 rounded-full animate-spin-slow"></div>
                  <div class="absolute w-[90%] h-[90%] border border-secondary/10 rounded-full animate-spin-slow-reverse"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom gradient line -->
    <!-- <div class="absolute bottom-0 left-0 right-0 h-px bg-linear-to-r from-transparent via-primary/50 to-transparent"></div> -->
  </div>
</template>

<style scoped>
@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

@keyframes float-slow {
  0%, 100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-10px) rotate(2deg);
  }
}

@keyframes float-particle {
  0% {
    transform: translateY(0px) translateX(0px) scale(0);
    opacity: 0;
  }
  20% {
    opacity: 0.6;
    transform: scale(1);
  }
  80% {
    opacity: 0.4;
  }
  100% {
    transform: translateY(-120px) translateX(30px) scale(0);
    opacity: 0;
  }
}

@keyframes spin-slow {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes spin-slow-reverse {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

.animate-float-slow {
  animation: float-slow 6s ease-in-out infinite;
}

.animate-float-particle {
  animation: float-particle 5s ease-in-out infinite;
}

.animate-spin-slow {
  animation: spin-slow 20s linear infinite;
}

.animate-spin-slow-reverse {
  animation: spin-slow-reverse 15s linear infinite;
}

.delay-500 {
  animation-delay: 0.5s;
}

.delay-1000 {
  animation-delay: 1s;
}

.delay-1500 {
  animation-delay: 1.5s;
}

.delay-2000 {
  animation-delay: 2s;
}
</style>