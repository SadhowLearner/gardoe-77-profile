<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Navbar from './components/Navbar.vue'
import { Button } from './components/ui/button'

import { ArrowUpRight, Menu } from 'lucide-vue-next'
import HeroSection from '@/components/sections/hero/HeroSection.vue'
import ProfileSection from './components/sections/profile/ProfileSection.vue'
import FeaturedMenuSection from '@/components/sections/menu/FeaturedMenuSection.vue'
import FavoriteMenuSection from './components/sections/menu/FavoriteMenuSection.vue'
import ReservationSection from './components/sections/reservation/ReservationSection.vue'
import GallerySection from './components/sections/gallery/GallerySection.vue'
import TestimonialsSection from './components/sections/testimonials/TestimonialsSection.vue'
import ContactSection from './components/sections/contact/ContactSection.vue'
import FooterSection from './components/sections/footer/FooterSection.vue'
</script>

<template>
  <main class="flex flex-col gap-42.5 pb-22.5">
    <HeroSection />
    <ProfileSection />
    <div class="flex flex-col gap-y-32">
      <FeaturedMenuSection />
      <FavoriteMenuSection />
    </div>
    <ReservationSection />
    <GallerySection />
    <TestimonialsSection />
    <ContactSection />
  </main>
  <FooterSection />
</template>
