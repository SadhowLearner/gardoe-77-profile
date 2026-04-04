<template>
  <section class="grid grid-cols-3 mt-48!">
    <div class="flex flex-col justify-center gap-4 col-span-1">
      <h2 class="text-2xl">
        Fasilitas Nyaman
        <br />
        untuk Nongkrong
      </h2>
      <p>Tempat ideal untuk santai & melepas penat.</p>
    </div>
    <div class="col-span-2 grid grid-cols-2 gap-y-6 gap-x-12 grid-rows-2">
      <div class="">
        <img :src="wifi" alt="" />
        <h3 class="text-lg my-4!">High-Speed Wifi</h3>
        <p>Internet gratis untuk semua pengunjung. Streaming dan untuk apapun pasti lancar jaya!</p>
      </div>
      <div class="">
        <img :src="motor" alt="" />
        <h3 class="text-lg my-4!">Parking Area</h3>
        <p class="max-w-xs">Area parkir strategis dengan akses yang mudah, dan tertata rapi.</p>
      </div>
      <div class="">
        <img :src="bulb" alt="" />
        <h3 class="text-lg my-4!">Power Outlets</h3>
        <p>Stop kontak disetiap meja. Laptop dan gadget anda aman, ga perlu rebutan colokan.</p>
      </div>
      <div class="">
        <img :src="music" alt="" />
        <h3 class="text-lg my-4!">Chill Vibes</h3>
        <p class="max-w-xs">
          Playlist yang pas buat kerja atau santai. Volume yang nyaman didengar.
        </p>
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
