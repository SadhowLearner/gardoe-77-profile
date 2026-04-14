<script setup lang="ts">
import hero from '@/assets/images/sections/hero.png'
import cust from '@/assets/images/sections/customer.png'
import rate from '@/assets/images/icons/rating.svg'
import Badge from '@/components/Badge.vue'
import Navbar from '@/components/Navbar.vue'
import wa from '@/assets/images/icons/wa-hero.svg'
import gofood from '@/assets/images/icons/gofood.svg'
</script>
<template>
  <section
    class="relative flex flex-col h-dvh lg:min-h-screen overflow-hidden px-4 sm:px-8 md:px-16 lg:px-20"
  >
    <div class="fixed bottom-10 right-16 flex flex-col items-end gap-8 z-50">
      <!-- Gojek-->
      <a
        href="https://gofood.co.id/malang/restaurant/kedai-kopi-gardoe77-5f7f9abf-e18a-4861-88db-2f8f73e1ca3d?ot=eyJtZXJjaGFudF9pZCI6IjFmY2UwYzMwLWNhYjItNDg0YS05ZGVmLWNiMDJkNDMxODllYSIsInVzZXJfaWQiOiIwIiwiZXhwaXJ5X3RpbWVfZXBvY2giOjE3MzY1ODQ5MjgsImRlbGl2ZXJ5X3ByaWNlIjo0MDAwLCJwYXJraW5nX2ZlZSI6MCwiZXRhX2J1ZmZlcl9taW5zIjo3LCJjdXN0b21lcl9sb2NhdGlvbiI6Ii02LjE4MjMxMywxMDYuODM2NDY0NiJ9.cl36bNO3JKyiggk%2F4zn0Iylm5tfOCq6bxTgqYWxPqaQ%3D"
        class="group flex overflow-visible items-center justify-start w-12 hover:w-52 h-12 rounded-full bg-[#EE2737] transition-all duration-300 shadow-lg"
      >
        <img :src="gofood" class="w-16 h-16 flex items-center justify-center shrink-0" />

        <span
          class="opacity-0 group-hover:opacity-100 ml-2 whitespace-nowrap text-white text-sm font-extrabold! w- transition-all duration-300"
        >
          Gofood Gardoe77
        </span>
      </a>

      <!-- WhatsApp -->
      <a
        href="https://wa.me/6285700816852"
        class="group flex items-center justify-start w-12 hover:w-52 h-12 rounded-full bg-[#25D366] transition-all duration-300 overflow-visible shadow-lg"
      >
        <img :src="wa" class="w-16 h-16 flex items-center justify-center shrink-0" />

        <span
          class="opacity-0 group-hover:opacity-100 ml-2 whitespace-nowrap text-white text-sm font-extrabold! transition-all duration-300"
        >
          WhatsApp Gardoe
        </span>
      </a>
    </div>
    <!-- Background -->
    <img
      :src="hero"
      alt="Kedai Kopi Gardoe 77"
      class="absolute inset-0 w-full h-full object-cover object-[65%_45%] md:object-[70%_8%]"
    />

    <!-- Overlay (biar text kebaca di mobile) -->
    <div class="absolute lg:hidden inset-0 bg-black/60 md:bg-black/40"></div>

    <Navbar />

    <!-- Content -->
    <div class="relative flex flex-1 items-end md:items-start pt-24 md:pt-32">
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
