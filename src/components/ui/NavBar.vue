<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { Button } from "@/components/ui/button";
import { Menu, X } from 'lucide-vue-next';

const isScrolled = ref(false);
const isMobileMenuOpen = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

const navItems = [
  { label: 'Services', href: '/services' },
  { label: 'Projects', href: '/projects' },
  { label: 'About Us', href: '/about' },
  { label: 'FAQ', href: '/faq' },
  { label: 'Blog', href: '/blog' },
];

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>

<template>
  <nav :class="[
    'fixed top-0 w-full z-50 transition-all duration-300',
    isScrolled
      ? 'bg-background/80 backdrop-blur-lg shadow-sm border-b border-border'
      : 'bg-transparent'
  ]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 lg:h-20">

        <!-- Logo Section -->
        <div class="flex items-center gap-3 group">
          <a href="/" class="flex items-center gap-3 transition-transform duration-300 hover:scale-105">
            <div class="relative">
              <div
                class="absolute inset-0 bg-primary opacity-0 group-hover:opacity-20 blur-xl transition-opacity duration-300 rounded-full">
              </div>
              <img src="../../assets/logo.png" alt="Conri Coding Logo"
                class="relative aspect-square size-10 lg:size-12 rounded-xl object-cover transition-all duration-300" />
            </div>
            <span class="text-xl lg:text-2xl font-bold text-foreground">
              Conri Coding
            </span>
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden lg:flex items-center gap-1">
          <a v-for="item in navItems" :key="item.label" :href="item.href">
            <Button variant="ghost"
              class="relative font-medium transition-colors duration-200 text-muted-foreground hover:text-foreground hover:bg-muted/50 rounded-full px-4">
              {{ item.label }}
            </Button>
          </a>
        </div>

        <!-- CTA Button (Desktop) -->
        <div class="hidden lg:flex items-center">
          <Button
            class="rounded-full px-6 shadow-lg shadow-primary/20 hover:shadow-primary/30 transition-all hover:-translate-y-0.5">
            <span class="relative z-10">Contact Us</span>
          </Button>
        </div>

        <!-- Mobile Menu Button -->
        <div class="flex lg:hidden">
          <button @click="toggleMobileMenu"
            class="p-2 rounded-lg text-foreground hover:bg-muted transition-colors duration-200"
            aria-label="Toggle menu">
            <Menu v-if="!isMobileMenuOpen" class="h-6 w-6" />
            <X v-else class="h-6 w-6" />
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition enter-active-class="transition duration-200 ease-out" enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0" leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 -translate-y-2">
      <div v-if="isMobileMenuOpen" class="lg:hidden border-t border-border bg-background/95 backdrop-blur-lg">
        <div class="px-4 py-6 space-y-3">
          <a v-for="item in navItems" :key="item.label" :href="item.href" @click="toggleMobileMenu" class="block">
            <Button variant="ghost"
              class="w-full justify-start text-left font-medium text-muted-foreground hover:text-foreground hover:bg-muted py-3 transition-all duration-200 rounded-xl">
              {{ item.label }}
            </Button>
          </a>
          <div class="pt-4 border-t border-border">
            <Button class="w-full rounded-full shadow-lg shadow-primary/20">
              Contact Us
            </Button>
          </div>
        </div>
      </div>
    </transition>
  </nav>

  <!-- Spacer to prevent content from going under fixed navbar -->
  <div class="h-16 lg:h-20"></div>
</template>

<style scoped>
/* Custom scrollbar for better aesthetics */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(to bottom, #3b82f6, #9333ea);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(to bottom, #2563eb, #7c3aed);
}

/* Smooth animations */
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>