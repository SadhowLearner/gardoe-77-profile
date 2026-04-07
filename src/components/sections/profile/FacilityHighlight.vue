<template>
  <section class="grid grid-cols-4 mt-24! gap-x-5">
    <div class="flex flex-col items-center justify-around gap-4 col-span-4 mb-15">
      <h2 class="text-3xl">Fasilitas Gardoe</h2>
      <p class="text-lg">Tempat ideal untuk santai & melepas penat.</p>
    </div>

    <div
      class="col-span-1 text-center flex flex-col items-center border rounded-2xl border-accent-foreground py-5 px-6.25"
    >
      <img :src="wifi" alt="" />
      <h3 class="text-xl text-foreground! mt-2">High-Speed Wifi</h3>
      <p>Internet gratis untuk semua</p>
    </div>
    <div
      class="col-span-1 text-center flex flex-col items-center border rounded-2xl border-accent-foreground py-5 px-6.25"
    >
      <img :src="motor" alt="" />
      <h3 class="text-xl text-foreground! mt-2">Parking Area</h3>
      <p class="max-w-xs">Stop kontak disetiap meja</p>
    </div>
    <div
      class="col-span-1 text-center flex flex-col items-center border rounded-2xl border-accent-foreground py-5 px-6.25"
    >
      <img :src="bulb" alt="" />
      <h3 class="text-xl text-foreground! mt-2">Power Outlets</h3>
      <p>Parkiran Area Strategis</p>
    </div>
    <div
      class="col-span-1 text-center flex flex-col items-center border rounded-2xl border-accent-foreground py-5 px-6.25"
    >
      <img :src="music" alt="" />
      <h3 class="text-xl text-foreground! mt-2">Chill Vibes</h3>
      <p class="max-w-xs">Playlist yang pas untukmu</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import wifi from '@/assets/images/icons/wifi.svg'
import motor from '@/assets/images/icons/motorcycle.svg'
import bulb from '@/assets/images/icons/bulb.svg'
import music from '@/assets/images/icons/music.svg'
</script>
