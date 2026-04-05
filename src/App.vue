<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Navbar from './components/Navbar.vue'
import { Button } from './components/ui/button'

import { ArrowUpRight, Menu } from 'lucide-vue-next'
import HeroSection from '@/components/sections/hero/HeroSection.vue'
import ProfileSection from './components/sections/profile/ProfileSection.vue'
import FeaturedMenuSection from '@/components/sections/menu/FeaturedMenuSection.vue'
</script>

<template>
  <!-- <header class="w-full max-h-[20vh] h-[18vh] flex justify-between work-sans">
    <div class="w-1/5">
      <Button variant="outline" class="m-5! size-10">
        <Menu class="size-8" />
      </Button>
    </div>
    <Navbar />
    <div class="flex justify-end w-1/5">
      <Button variant="outline" class="m-3!"> Kontak <ArrowUpRight /> </Button>
    </div>
  </header> -->
  <main class="px-20 flex flex-col gap-24">
    <!-- <HeroSection /> -->

    <ProfileSection />
    <FeaturedMenuSection />
    <div class="h-[300vh] w-full" />
  </main>
</template>
