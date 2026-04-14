<script setup lang="ts">
import hero from '@/assets/images/sections/hero.png'
import cust from '@/assets/images/sections/customer.png'
import rate from '@/assets/images/icons/rating.svg'
import Badge from '@/components/Badge.vue'
import Navbar from '@/components/Navbar.vue'
</script>
<template>
  <section class="relative flex flex-col h-[60dvh] lg:min-h-screen overflow-hidden">
    <!-- Background -->
    <img
      :src="hero"
      alt="Kedai Kopi Gardoe 77"
      class="absolute inset-0 w-full h-full object-cover object-[65%_20%] md:object-[70%_8%]"
    />

    <!-- Overlay (biar text kebaca di mobile) -->
    <div class="absolute lg:hidden inset-0 bg-black/60 md:bg-black/40"></div>

    <Navbar />

    <!-- Content -->
    <div class="relative flex flex-1 items-start pt-24 md:pt-32 px-4 sm:px-8 md:px-16 lg:px-20">
      <div class="flex flex-col gap-6 md:gap-10 max-w-xl lg:max-w-2xl">
        <Badge>Singgah, Ngopi, Bercerita</Badge>

        <!-- Heading -->
        <h1 class="text-3xl sm:text-5xl md:text-6xl lg:text-8xl text-white! leading-tight">
          GARDOE
          <span class="inline-block -translate-y-1 md:-translate-y-3 font-extrabold!"> 77 </span>
          <br />
          <span class="font-extrabold!">PAKISADJI</span>
        </h1>

        <!-- Customer -->
        <div class="flex items-center gap-3 md:gap-4">
          <img :src="cust" alt="customers" class="w-20 md:w-auto" />

          <div>
            <img :src="rate" alt="rating" class="mb-1 md:mb-2 w-24 md:w-auto" />
            <h4 class="text-xs sm:text-sm md:text-base text-white/90">1000+ pelanggan bergabung</h4>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
