<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { ArrowLeft, ArrowRight, Quote } from 'lucide-vue-next'
import { Button } from '@/components/ui/button'
import { Card, CardHeader, CardContent } from '@/components/ui/card'

const testimonials = [
    {
        quote: "We saw businesses drowning in data but struggling to make sense of it. Decisions were slow, teams were overwhelmed, and opportunities were missed.",
        author: "John Doe",
        role: "Founder & CEO"
    },
    {
        quote: "That's when we realized there had to be a better way—a smarter, faster, more intuitive solution that brings clarity to chaos.",
        author: "Jane Smith",
        role: "Co-Founder"
    },
    {
        quote: "So we built a platform that empowers companies to transform raw data into real-time strategic decisions using the power of AI.",
        author: "Mike Johnson",
        role: "CTO"
    },
    {
        quote: "Our mission is to democratize data analytics, making it accessible to everyone, ensuring every decision is backed by facts.",
        author: "Sarah Williams",
        role: "Head of Product"
    }
]

const currentIndex = ref(0)
const itemsPerView = ref(1)

const updateItemsPerView = () => {
    if (window.innerWidth >= 1024) {
        itemsPerView.value = 3
    } else if (window.innerWidth >= 768) {
        itemsPerView.value = 2
    } else {
        itemsPerView.value = 1
    }
}

onMounted(() => {
    updateItemsPerView()
    window.addEventListener('resize', updateItemsPerView)
})

onUnmounted(() => {
    window.removeEventListener('resize', updateItemsPerView)
})

const next = () => {
    const maxIndex = testimonials.length - itemsPerView.value
    if (currentIndex.value < maxIndex) {
        currentIndex.value++
    } else {
        currentIndex.value = 0
    }
}

const prev = () => {
    if (currentIndex.value > 0) {
        currentIndex.value--
    } else {
        currentIndex.value = testimonials.length - itemsPerView.value
    }
}
</script>

<template>
    <section class="py-24 bg-gradient-to-b from-background to-muted/20">
        <div class="container mx-auto max-w-7xl px-4">

            <!-- Header -->
            <div class="text-center mb-20 space-y-6">
                <div
                    class="inline-flex items-center gap-2 px-4 py-2 bg-primary/10 rounded-full mb-4 border border-primary/20">
                    <span class="w-2 h-2 rounded-full bg-primary animate-pulse"></span>
                    <span class="text-sm font-semibold text-primary tracking-wide">Our Journey</span>
                </div>
                <h2 class="text-4xl md:text-6xl font-black tracking-tight text-foreground leading-tight">
                    Built for your <span
                        class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Success</span>
                </h2>
                <p class="text-muted-foreground max-w-2xl mx-auto text-lg md:text-xl leading-relaxed">
                    We combine deep technical expertise with sharp business acumen to deliver exceptional value and
                    solutions that exceed expectations.
                </p>
            </div>

            <!-- Carousel Container -->
            <div class="relative max-w-7xl mx-auto">

                <!-- Cards Wrapper -->
                <div class="overflow-hidden px-4 md:px-12 py-8"> <!-- Added py-8 for shadow space -->
                    <div class="flex gap-6 transition-transform duration-700 ease-in-out"
                        :style="{ transform: `translateX(-${currentIndex * (100 / itemsPerView)}%)` }">
                        <div v-for="(testimonial, index) in testimonials" :key="index" class="flex-shrink-0"
                            :style="{ width: `calc((100% - ${(itemsPerView - 1) * 24}px) / ${itemsPerView})` }">
                            <Card
                                class="h-full border-muted hover:border-primary/50 hover:shadow-xl transition-all duration-300 group bg-card/50 backdrop-blur-sm">

                                <CardHeader class="pb-2 pt-8 relative">
                                    <div
                                        class="absolute top-6 right-6 opacity-10 group-hover:opacity-20 transition-opacity">
                                        <Quote class="w-16 h-16 text-primary" />
                                    </div>
                                    <div
                                        class="w-12 h-12 rounded-2xl bg-gradient-to-br from-primary to-secondary flex items-center justify-center shadow-lg transform group-hover:-translate-y-1 transition-transform duration-300">
                                        <Quote class="w-6 h-6 text-white" />
                                    </div>
                                </CardHeader>

                                <CardContent class="px-8 pb-10 flex flex-col h-full">
                                    <p
                                        class="text-muted-foreground text-lg leading-relaxed mb-8 flex-grow relative z-10 pt-4">
                                        "{{ testimonial.quote }}"
                                    </p>

                                    <div class="flex items-center gap-4 pt-6 border-t border-border/50 mt-auto">
                                        <div
                                            class="w-10 h-10 rounded-full bg-secondary/20 flex items-center justify-center text-secondary font-bold">
                                            {{ testimonial.author.charAt(0) }}
                                        </div>
                                        <div>
                                            <p class="font-bold text-foreground text-lg">{{ testimonial.author }}</p>
                                            <p class="text-sm text-primary font-medium">{{ testimonial.role }}</p>
                                        </div>
                                    </div>
                                </CardContent>

                            </Card>
                        </div>
                    </div>
                </div>

                <!-- Navigation Buttons -->
                <button @click="prev"
                    class="absolute left-0 top-1/2 -translate-y-1/2 w-12 h-12 rounded-full bg-background border border-border shadow-lg flex items-center justify-center hover:bg-primary hover:text-white hover:border-primary transition-all duration-300 transform hover:scale-110 z-20 group"
                    aria-label="Previous">
                    <ArrowLeft class="w-6 h-6 group-hover:-translate-x-0.5 transition-transform" />
                </button>

                <button @click="next"
                    class="absolute right-0 top-1/2 -translate-y-1/2 w-12 h-12 rounded-full bg-background border border-border shadow-lg flex items-center justify-center hover:bg-primary hover:text-white hover:border-primary transition-all duration-300 transform hover:scale-110 z-20 group"
                    aria-label="Next">
                    <ArrowRight class="w-6 h-6 group-hover:translate-x-0.5 transition-transform" />
                </button>
            </div>

            <!-- CTA Button -->
            <div class="text-center mt-16">
                <Button size="lg"
                    class="px-8 py-6 text-lg rounded-full shadow-lg shadow-primary/20 hover:shadow-primary/40 hover:-translate-y-1 transition-all">
                    Learn More
                    <ArrowRight class="w-5 h-5 ml-2" />
                </Button>
            </div>

        </div>
    </section>
</template>
