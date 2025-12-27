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
  <nav 
    :class="[
      'fixed top-0 w-full z-50 transition-all duration-300',
      isScrolled 
        ? 'bg-white/80 dark:bg-gray-900/80 backdrop-blur-lg shadow-lg border-b border-gray-800/50' 
        : 'bg-white/60 dark:bg-gray-900/60 backdrop-blur-sm border-b border-gray-400/50'
    ]"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 lg:h-20">
        
        <!-- Logo Section -->
        <div class="flex items-center gap-3 group">
          <a href="/" class="flex items-center gap-3 transition-transform duration-300 hover:scale-105">
            <div class="relative">
              <div class="absolute inset-0 opacity-0 group-hover:opacity-20 blur-xl transition-opacity duration-300"></div>
              <img
                src="../../assets/logo.png"
                alt="Conri Coding Logo"
                class="relative aspect-square size-10 lg:size-12 rounded-xl object-cover transition-all duration-300"
              />
            </div>
            <span class="text-xl lg:text-2xl font-bold">
              Conri Coding
            </span>
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden lg:flex items-center gap-4">
          <a 
            v-for="item in navItems" 
            :key="item.label"
            :href="item.href"
          >
            <Button 
              variant="ghost" 
              class="relative font-medium transition-colors duration-200"
            >
              {{ item.label }}
            </Button>
          </a>
        </div>

        <!-- CTA Button (Desktop) -->
        <div class="hidden lg:flex items-center">
          <Button 
          >
            <span class="relative z-10">Contact Us</span>
          </Button>
        </div>

        <!-- Mobile Menu Button -->
        <div class="flex lg:hidden">
          <button
            @click="toggleMobileMenu"
            class="p-2 rounded-lg text-gray-700 hover:bg-gray-100 transition-colors duration-200"
            aria-label="Toggle menu"
          >
            <Menu v-if="!isMobileMenuOpen" class="h-6 w-6" />
            <X v-else class="h-6 w-6" />
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div 
        v-if="isMobileMenuOpen"
        class="lg:hidden border-t border-gray-200/50 bg-white/95 backdrop-blur-lg"
      >
        <div class="px-4 py-6 space-y-3">
          <a 
            v-for="item in navItems" 
            :key="item.label"
            :href="item.href"
            @click="toggleMobileMenu"
            class="block"
          >
            <Button 
              variant="ghost" 
              class="w-full justify-start text-left font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 py-3 transition-all duration-200"
            >
              {{ item.label }}
            </Button>
          </a>
          <div class="pt-4 border-t border-gray-200">
            <Button>
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