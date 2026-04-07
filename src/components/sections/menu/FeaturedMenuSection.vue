<template>
  <section class="px-20">
    <div class="flex flex-col gap-5 items-center text-center">
      <Badge> Pilihan Menu Kami </Badge>
      <h2 class="text-5xl leading-16">
        Dari Secangkir Kopi <br />
        Hingga Hidangan Lezat
      </h2>
      <h4 class="mt-2 leading-8">
        Nikmati berbagai menu makanan dan minuman yang pas <br />
        untuk bersantai sambil menikmati suasana Gardoe77
      </h4>
      <MenubarCoffee />
    </div>
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
import MenubarCoffee from './MenubarCoffee.vue'
import MenuList from './MenuList.vue'
</script>
