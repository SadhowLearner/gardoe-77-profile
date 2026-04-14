<template>
  <footer
    class="bg-white/20 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 items-center gap-4 sm:gap-6 px-2 sm:px-4 md:px-8 lg:px-20 py-4 sm:py-6"
  >
    <!-- Social -->
    <div class="col-span-1 flex items-center justify-center gap-2.5">
      <img :src="instagram" alt="instagram" class="w-5 h-5 sm:w-6 sm:h-6" />
      <p class="text-sm sm:text-base md:text-lg lg:text-[24px]">@Gardoe77</p>
    </div>

    <div class="col-span-1 flex items-center justify-center gap-2.5">
      <img :src="facebook" alt="facebook" class="w-5 h-5 sm:w-6 sm:h-6" />
      <p class="text-sm sm:text-base md:text-lg lg:text-[24px]">Gardoe77</p>
    </div>

    <!-- Email -->
    <div
      class="col-span-2 md:col-span-1 flex justify-center items-center gap-2.5 text-center sm:text-right"
    >
      <img :src="email" alt="email" class="w-5 h-5 sm:w-6 sm:h-6" />
      <p class="text-sm sm:text-base md:text-lg lg:text-[24px] break-all">
        Gardoe77pakisaji@gmail.com
      </p>
    </div>
  </footer>
</template>

<script setup lang="ts">
import email from '@/assets/images/icons/email.svg'
import facebook from '@/assets/images/icons/facebook.svg'
import instagram from '@/assets/images/icons/instagram.svg'
</script>

<style scoped></style>
