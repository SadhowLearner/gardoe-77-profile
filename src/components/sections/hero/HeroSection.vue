<script setup lang="ts">
import hero from '@/assets/images/sections/hero.png'
</script>

<template>
  <section class="relative h-screen min-h-175 overflow-hidden">
    <!-- Background Image -->
    <img
      :src="hero"
      alt="Kedai Kopi Gardoe 77"
      class="absolute inset-0 h-full w-full object-cover"
    />

    <!-- Dark Overlay -->
    <div class="absolute inset-0 bg-black/80" />

    <!-- Content Wrapper -->
    <div class="relative z-10 flex h-full flex-col justify-center">
      <!-- Top Info Bar -->
      <div class="flex justify-center px-4">
        <p
          class="bg-[#31190F]/90 w-full py-3 text-center text-xl font-medium text-white! shadow-lg backdrop-blur-sm md:text-base"
        >
          Buka Setiap Hari, Senin–Jum’at 08.00–23.00 • Sabtu–Minggu 07.00–23.00
        </p>
      </div>

      <!-- Hero Main Content -->
      <div class="mx-auto flex flex-1 items-center justify-center md:px-12">
        <div class="max-w-5xl">
          <h1 class="text-7xl text-white! text-center">
            Perjalanan Boleh Singkat, Tapi Rasa Kopi Tetap Melekat
          </h1>
        </div>
      </div>
      <p class="font-medium text-2xl text-center text-white! work-sans pb-16">SINCE 2020</p>
    </div>
  </section>
</template>
