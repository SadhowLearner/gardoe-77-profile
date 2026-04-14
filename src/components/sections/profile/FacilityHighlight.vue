<template>
  <section class="mt-16 md:mt-24 px-4 md:px-10 lg:px-20">
    <!-- Header -->
    <div class="flex flex-col items-center text-center gap-3 md:gap-4 mb-10 md:mb-15">
      <h2 class="text-2xl md:text-3xl font-semibold">Fasilitas Gardoe</h2>
      <p class="text-sm md:text-lg max-w-md">Tempat ideal untuk santai & melepas penat.</p>
    </div>

    <!-- Grid -->
    <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-5">
      <!-- Card -->
      <div class="facility-card">
        <img :src="wifi" alt="Wifi" class="w-10 h-10 mb-2" />
        <h3 class="title">High-Speed Wifi</h3>
        <p class="desc">Internet gratis untuk semua</p>
      </div>

      <div class="facility-card">
        <img :src="motor" alt="Parking" class="w-10 h-10 mb-2" />
        <h3 class="title">Parking Area</h3>
        <p class="desc">Parkiran area strategis</p>
      </div>

      <div class="facility-card">
        <img :src="bulb" alt="Power" class="w-10 h-10 mb-2" />
        <h3 class="title">Power Outlets</h3>
        <p class="desc">Stop kontak di setiap meja</p>
      </div>

      <div class="facility-card">
        <img :src="music" alt="Music" class="w-10 h-10 mb-2" />
        <h3 class="title">Chill Vibes</h3>
        <p class="desc">Playlist yang pas untukmu</p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import wifi from '@/assets/images/icons/wifi.svg'
import motor from '@/assets/images/icons/motorcycle.svg'
import bulb from '@/assets/images/icons/bulb.svg'
import music from '@/assets/images/icons/music.svg'
</script>

<style scoped>
@reference '@/assets/main.css';

.facility-card {
  @apply flex flex-col items-center text-center border rounded-2xl border-accent-foreground 
         py-5 px-5 md:px-6 transition hover:shadow-md;
}

.title {
  @apply text-base md:text-lg font-medium mt-2;
}

.desc {
  @apply text-sm md:text-base text-muted-foreground;
}
</style>
