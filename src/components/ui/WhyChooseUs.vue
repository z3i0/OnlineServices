<script setup lang="ts">
import { BadgeCheck, Zap, Users, ShieldCheck } from 'lucide-vue-next'
import { Card, CardHeader, CardContent } from '@/components/ui/card'

const features = [
    {
        title: 'Innovation',
        description: 'Pushing boundaries in AI, blockchain, and quantitative trading to deliver cutting-edge solutions.',
        icon: Zap
    },
    {
        title: 'Collaboration',
        description: 'Working closely with clients to develop tailored solutions that drive measurable success.',
        icon: Users
    },
    {
        title: 'Excellence',
        description: 'Maintaining the highest standards in code quality, system performance, and client outcomes.',
        icon: BadgeCheck
    },
    {
        title: 'Integrity',
        description: 'Operating with transparency and ethical considerations at the forefront of all decisions.',
        icon: ShieldCheck
    }
]
</script>

<template>
    <section class="py-24 relative overflow-hidden">
        <!-- Background Elements -->
        <div class="absolute inset-0 -z-10"></div>
        <div class="absolute top-0 left-0 w-full h-px">
        </div>
        <div class="absolute bottom-0 left-0 w-full h-px">
        </div>

        <div class="container mx-auto max-w-7xl px-4 md:px-6">

            <!-- Section Header -->
            <div class="text-center mb-16 space-y-6">
                <div
                    class="inline-flex items-center gap-2 px-4 py-2 bg-primary/10 rounded-full mb-4 border border-primary/20">
                    <span class="w-2 h-2 rounded-full bg-primary animate-pulse"></span>
                    <span class="text-sm font-semibold text-primary tracking-wide">Why Choose Us</span>
                </div>
                <h2 class="text-4xl md:text-5xl font-black tracking-tight text-foreground leading-tight">
                    Built for your <span
                        class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Success</span>
                </h2>
                <p class="text-muted-foreground max-w-2xl mx-auto text-lg leading-relaxed">
                    We combine technical expertise with business acumen to deliver exceptional value.
                </p>
            </div>

            <!-- Features Grid -->
            <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-4">
                <Card v-for="(feature, index) in features" :key="index"
                    class="group relative overflow-hidden border-primary/10 bg-card/40 backdrop-blur-sm transition-all duration-300 hover:shadow-2xl hover:shadow-primary/5 hover:-translate-y-1 hover:border-primary/30">

                    <!-- Gradient Hover Effect -->
                    <div
                        class="absolute inset-0 bg-gradient-to-br from-primary/5 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500">
                    </div>

                    <CardHeader class="relative z-10 pb-2">
                        <div
                            class="w-12 h-12 mb-4 rounded-xl bg-primary/10 flex items-center justify-center group-hover:bg-primary group-hover:text-primary-foreground transition-all duration-300">
                            <component :is="feature.icon" :size="24" stroke-width="2" />
                        </div>
                        <h3 class="text-xl font-bold text-foreground">{{ feature.title }}</h3>
                    </CardHeader>

                    <CardContent class="relative z-10">
                        <p class="text-muted-foreground leading-relaxed">
                            {{ feature.description }}
                        </p>
                    </CardContent>
                </Card>
            </div>

        </div>
    </section>
</template>