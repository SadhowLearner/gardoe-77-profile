<script setup lang="ts">
import hero from '@/assets/images/sections/hero.png'
import cust from '@/assets/images/sections/customer.png'
import rate from '@/assets/images/icons/rating.svg'
import Badge from '@/components/Badge.vue'
import Navbar from '@/components/Navbar.vue'
</script>

<template>
  <section class="relative h-screen min-h-175 overflow-hidden">
    <!-- Background Image -->

    <img
      :src="hero"
      alt="Kedai Kopi Gardoe 77"
      class="absolute inset-0 h-full w-full object-cover object-[70%_8%]"
    />

    <div
      class="border absolute right-120 bottom-94 border-white/10 bg-white/28 rounded-xl text-lg! px-5 py-3 font-normal"
    >
      Kopi temani perjalanan
    </div>
    <div
      class="border absolute right-28 top-108 border-white/10 bg-white/28 rounded-xl text-lg! px-5 py-3 font-normal"
    >
      Suasana Hangat Vintage
    </div>

    <Navbar />

    <!-- Content Wrapper -->
    <div class="relative flex h-full items-center ps-20 justify-start">
      <!-- Hero Main Content -->
      <div class="flex flex-col gap-11.25 min-w-114.25">
        <Badge>Singgah, Ngopi, Bercerita</Badge>
        <h1 class="text-8xl! text-white! leading-[120%] text-center">
          GARDOE <span class="pb-14 font-bold!">77</span> <br />
          <span class="pe-4 font-bold!">PAKISADJI</span>
        </h1>
        <div class="flex gap-4">
          <img :src="cust" alt="" />
          <div>
            <img :src="rate" alt="" class="mb-3" />
            <h4>1000+ pelanggan bergabung</h4>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
