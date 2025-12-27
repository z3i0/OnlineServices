<script setup lang="ts">
import { Button } from "@/components/ui/button";
import { Separator } from "@/components/ui/separator";
import { Mail, Phone, Facebook, Instagram, Linkedin } from 'lucide-vue-next';

interface FooterLink {
    label: string;
    href: string;
}

const companyLinks: FooterLink[] = [
    { label: 'About Us', href: '/about' },
    { label: 'Services', href: '/services' },
    { label: 'Projects', href: '/projects' },
    { label: 'Blog', href: '/blog' },
];

const supportLinks: FooterLink[] = [
    { label: 'FAQ', href: '/faq' },
    { label: 'Contact', href: '/contact' },
    { label: 'Privacy Policy', href: '/privacy' },
    { label: 'Terms of Service', href: '/terms' },
];

const socialLinks = [
    { 
        name: 'Facebook', 
        href: 'https://www.facebook.com/people/Conri-Coding/100092009482063',
        icon: Facebook
    },
    { 
        name: 'Instagram', 
        href: 'https://www.instagram.com/conricoding',
        icon: Instagram
    },
    { 
        name: 'LinkedIn', 
        href: 'https://www.linkedin.com/in/conri-coding-9463b5252',
        icon: Linkedin
    },
];

const currentYear = new Date().getFullYear();
</script>

<template>
    <footer class="w-full bg-background border-t">
        <div class="container max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 lg:py-16">
            <!-- Main Footer Content -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12">
                <!-- Brand Section -->
                <div class="space-y-4 lg:col-span-1">
                    <a href="/" class="inline-flex items-center gap-3 group">
                        <div class="relative">
                            <div class="absolute inset-0 bg-primary rounded-xl opacity-0 group-hover:opacity-20 blur-xl transition-opacity duration-300"></div>
                            <img 
                                src="../../assets/logo.png" 
                                alt="Conri Coding Logo"
                                class="relative w-12 h-12 rounded-xl object-cover transition-transform duration-300 group-hover:scale-105" 
                            />
                        </div>
                        <span class="text-xl font-bold text-foreground">Conri Coding</span>
                    </a>
                    <p class="text-sm text-muted-foreground leading-relaxed max-w-xs">
                        Building innovative digital solutions with cutting-edge technology and creative excellence.
                    </p>
                </div>

                <!-- Company Links -->
                <div class="space-y-4">
                    <h3 class="text-sm font-semibold text-foreground uppercase tracking-wider">Company</h3>
                    <ul class="space-y-3">
                        <li v-for="link in companyLinks" :key="link.label">
                            <a 
                                :href="link.href"
                                class="text-sm text-muted-foreground hover:text-foreground transition-colors duration-200"
                            >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <!-- Support Links -->
                <div class="space-y-4">
                    <h3 class="text-sm font-semibold text-foreground uppercase tracking-wider">Support</h3>
                    <ul class="space-y-3">
                        <li v-for="link in supportLinks" :key="link.label">
                            <a 
                                :href="link.href"
                                class="text-sm text-muted-foreground hover:text-foreground transition-colors duration-200"
                            >
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <!-- Contact & Social -->
                <div class="space-y-4">
                    <h3 class="text-sm font-semibold text-foreground uppercase tracking-wider">Get in Touch</h3>
                    <div class="space-y-3">
                        <a 
                            href="mailto:conricoding@gmail.com"
                            class="flex items-center gap-2 text-sm text-muted-foreground hover:text-foreground transition-colors duration-200"
                        >
                            <Mail class="w-4 h-4" />
                            <span>conricoding@gmail.com</span>
                        </a>
                        <a 
                            href="tel:+10000000000"
                            class="flex items-center gap-2 text-sm text-muted-foreground hover:text-foreground transition-colors duration-200"
                        >
                            <Phone class="w-4 h-4" />
                            <span>+1 (000) 000-0000</span>
                        </a>
                    </div>
                    
                    <!-- Social Links -->
                    <div class="flex items-center gap-2 pt-2">
                        <Button
                            v-for="social in socialLinks"
                            :key="social.name"
                            variant="outline"
                            size="icon"
                            :as="'a'"
                            :href="social.href"
                            target="_blank"
                            rel="noopener noreferrer"
                            class="hover:text-primary"
                        >
                            <component :is="social.icon" class="w-4 h-4" />
                            <span class="sr-only">{{ social.name }}</span>
                        </Button>
                    </div>
                </div>
            </div>

            <!-- Footer Bottom -->
            <Separator class="my-8" />
            
            <div class="flex flex-col sm:flex-row items-center justify-between gap-4">
                <p class="text-sm text-muted-foreground text-center sm:text-left">
                    © {{ currentYear }} Conri Coding. All rights reserved.
                </p>
                <div class="flex items-center gap-1">
                    <Button 
                        variant="link" 
                        size="sm"
                        as="a"
                        href="/privacy"
                        class="text-xs text-muted-foreground hover:text-foreground"
                    >
                        Privacy
                    </Button>
                    <span class="text-muted-foreground">•</span>
                    <Button 
                        variant="link" 
                        size="sm"
                        as="a"
                        href="/terms"
                        class="text-xs text-muted-foreground hover:text-foreground"
                    >
                        Terms
                    </Button>
                    <span class="text-muted-foreground">•</span>
                    <Button 
                        variant="link" 
                        size="sm"
                        as="a"
                        href="/cookies"
                        class="text-xs text-muted-foreground hover:text-foreground"
                    >
                        Cookies
                    </Button>
                </div>
            </div>
        </div>
    </footer>
</template>