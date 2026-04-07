<template>
  <section id="profil" class="my-24 px-20">
    <div class="flex flex-col justify-center w-full items-center gap-7 mb-16!">
      <Badge> Profil Kami </Badge>
      <h2 class="text-5xl">Lebih Dari Sekedar Kedai kopi</h2>
      <h4>
        Bukan sekadar tempat ngopi, tapi ruang untuk cerita, tawa, dan momen yang ingin diulang.
      </h4>
    </div>
    <div class="grid grid-cols-2 gap-x-15">
      <div class="flex flex-col justify-end mt-auto gap-y-17.5 col-span-1 w-138.25 h-83.25">
        <div>
          <h3 class="text-3xl mb-6.75">Tempat Nongkrong yang Kamu Cari</h3>
          <p class="text-lg leading-[180%]! mb-2">
            Gardoe77 Pakisadji hadir sebagai ruang hangat untuk kamu yang ingin melepas penat,
            berbagi cerita, atau sekadar menikmati waktu sendiri. Dengan suasana nyaman bernuansa
            vintage, pemandangan kereta api yang melintas, tempat ini menawarkan pengalaman
            nongkrong yang berbeda, unik, dan penuh cerita.
          </p>
          <p class="text-lg leading-[180%]!">
            Secangkir kopi bukan hanya minuman, tapi teman setia untuk menikmati setiap momen,
            termasuk saat melihat perjalanan kereta yang berlalu dengan suasana menenangkan.
          </p>
        </div>
        <StatsHighlight />
      </div>
      <div class="col-span-1">
        <img :src="profileImg" alt="" class="w-154 h-139" />
      </div>
    </div>
    <FacilityHighlight />
  </section>
</template>

<script setup lang="ts">
import profileImg from '@/assets/images/sections/profile.png'
import StatsHighlight from './StatsHighlight.vue'
import FacilityHighlight from './FacilityHighlight.vue'
import Badge from '@/components/Badge.vue'
</script>

<style scoped></style>
