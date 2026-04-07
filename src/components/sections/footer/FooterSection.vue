<template>
  <footer class="bg-white/20 flex justify-between px-25 py-6">
    <div class="flex gap-2.5 items-center">
      <img :src="instagram" alt="instagram" />
      <p class="text-[24px]">@Gardoe77</p>
    </div>
    <div class="flex gap-2.5 items-center">
      <img :src="facebook" alt="instagram" />
      <p class="text-[24px]">Gardoe77</p>
    </div>
    <div class="flex gap-2.5 items-center">
      <img :src="email" alt="instagram" />
      <p class="text-[24px]">Gardoe77pakisaji@gmail.com</p>
    </div>
  </footer>
</template>

<script setup lang="ts">
import email from '@/assets/images/icons/email.svg'
import facebook from '@/assets/images/icons/facebook.svg'
import instagram from '@/assets/images/icons/instagram.svg'
</script>

<style scoped></style>
