<template>
  <section class="px-8 md:px-16 lg:px-20">
    <div class="flex flex-col gap-5 items-center text-center">
      <div class="text-center">
        <Badge>Pilihan Menu Kami</Badge>

        <h2
          class="text-3xl sm:text-4xl md:text-5xl leading-tight md:leading-[1.2] mt-4 font-semibold"
        >
          Dari Secangkir Kopi <br class="hidden sm:block" />
          Hingga Hidangan Lezat
        </h2>

        <h4 class="text-sm sm:text-base md:text-lg mt-3 md:mt-4 max-w-xl leading-relaxed">
          Nikmati berbagai menu makanan dan minuman yang pas <br class="hidden sm:block" />
          untuk bersantai sambil menikmati suasana Gardoe77
        </h4>
      </div>
      <MenubarCoffee />
    </div>
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
import MenubarCoffee from './MenubarCoffee.vue'
</script>
