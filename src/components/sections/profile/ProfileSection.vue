<template>
  <section class="py-24">
    <div class="flex flex-col justify-center w-full items-center gap-7 mb-16!">
      <p class="rounded-full border border-[#E4D9D5] text-brown-secondary! px-5 py-1">
        Profil Kami
      </p>
      <h1 class="text-5xl text-brown-primary">Lebih Dari Sekedar Kedai kopi</h1>
      <p class="text-accent">
        Bukan sekadar tempat ngopi, tapi ruang untuk cerita, tawa, dan momen yang ingin diulang.
      </p>
    </div>
    <div class="grid grid-cols-2 gap-10 relative">
      <div class="flex flex-col gap-8 justify-start mt-28! col-span-1 max-w-xl">
        <h3 class="text-3xl">Tempat Nongkrong yang Kamu Cari</h3>
        <p>
          Gardoe77 Pakisadji hadir sebagai ruang hangat untuk kamu yang ingin melepas penat, berbagi
          cerita, atau sekadar menikmati waktu sendiri. Dengan suasana nyaman bernuansa vintage,
          pemandangan kereta api yang melintas, tempat ini menawarkan pengalaman nongkrong yang
          berbeda, unik, dan penuh cerita. Secangkir kopi bukan hanya minuman, tapi teman setia
          untuk menikmati setiap momen, termasuk saat melihat perjalanan kereta yang berlalu dengan
          suasana menenangkan.
        </p>
        <p>
          Gardoe77, tempat singgah nyaman untuk istirahat, mengisi energi, atau menunggu perjalanan
          berikutnya dengan suasana tenang.
        </p>
      </div>
      <div class="col-span-1">
        <img :src="profileImg" alt="" />
      </div>
      <StatsHighlight />
    </div>
  </section>
</template>

<script setup lang="ts">
import profileImg from '@/assets/images/sections/profile.png'
import StatsHighlight from './StatsHighlight.vue'
</script>

<style scoped></style>
