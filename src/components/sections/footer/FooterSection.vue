<template>
  <footer
    class="bg-white/20 flex flex-col sm:flex-row sm:flex-wrap lg:flex-nowrap items-center sm:items-center justify-center lg:justify-between gap-4 sm:gap-6 px-4 sm:px-8 md:px-12 lg:px-25 py-4 sm:py-6"
  >
    <!-- Social (IG + FB) -->
    <div class="flex flex-row justify-evenly w-full items-center gap-3 sm:gap-6">
      <div class="flex items-center gap-2.5">
        <img :src="instagram" alt="instagram" class="w-5 h-5 sm:w-6 sm:h-6" />
        <p class="text-sm sm:text-base md:text-lg lg:text-[24px]">@Gardoe77</p>
      </div>

      <div class="flex items-center gap-2.5">
        <img :src="facebook" alt="facebook" class="w-5 h-5 sm:w-6 sm:h-6" />
        <p class="text-sm sm:text-base md:text-lg lg:text-[24px]">Gardoe77</p>
      </div>
    </div>

    <!-- Email -->
    <div class="flex items-center justify-center w-full sm:w-auto gap-2.5 break-all text-center">
      <img :src="email" alt="email" class="w-5 h-5 sm:w-6 sm:h-6" />
      <p class="text-sm sm:text-base md:text-lg lg:text-[24px]">Gardoe77pakisaji@gmail.com</p>
    </div>
  </footer>
</template>

<script setup lang="ts">
import email from '@/assets/images/icons/email.svg'
import facebook from '@/assets/images/icons/facebook.svg'
import instagram from '@/assets/images/icons/instagram.svg'
</script>

<style scoped></style>
