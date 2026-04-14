<template>
  <section id="profil" class="px-8 md:px-16 lg:px-20">
    <!-- Header -->
    <div
      class="flex flex-col items-center text-center gap-4 md:gap-6 mb-10 md:mb-16 px-4 sm:px-8 md:px-12 lg:px-20"
    >
      <Badge>Profil Kami</Badge>

      <h2 class="text-3xl sm:text-4xl md:text-5xl font-semibold">Lebih Dari Sekedar Kedai kopi</h2>

      <h4 class="text-sm sm:text-base md:text-lg max-w-xl leading-[180%]">
        Bukan sekadar tempat ngopi, tapi ruang untuk cerita, tawa, dan momen yang ingin diulang.
      </h4>
    </div>

    <!-- Content -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-14 lg:gap-x-16 items-center">
      <!-- Text -->
      <div
        class="flex flex-col order-2 lg:order-1 justify-between gap-6 md:gap-8 h-full max-w-xl mx-auto"
      >
        <div class="text-center lg:text-left">
          <h3 class="text-lg sm:text-xl md:text-2xl lg:text-3xl font-semibold mb-3 md:mb-5">
            Tempat Nongkrong yang Kamu Cari
          </h3>

          <p class="text-sm sm:text-base md:text-lg leading-relaxed mb-3 md:mb-4 text-white/80">
            Gardoe77 Pakisadji hadir sebagai ruang hangat untuk kamu yang ingin melepas penat,
            berbagi cerita, atau sekadar menikmati waktu sendiri. Dengan suasana nyaman bernuansa
            vintage, pemandangan kereta api yang melintas, tempat ini menawarkan pengalaman
            nongkrong yang berbeda, unik, dan penuh cerita.
          </p>

          <p class="text-sm sm:text-base md:text-lg leading-relaxed text-white/80">
            Secangkir kopi bukan hanya minuman, tapi teman setia untuk menikmati setiap momen,
            termasuk saat melihat perjalanan kereta yang berlalu dengan suasana menenangkan.
          </p>
        </div>

        <StatsHighlight />
      </div>

      <!-- Image -->
      <div class="w-full order-1 lg:order-2 flex items-center justify-center px-4 lg:px-0">
        <img
          :src="profileImg"
          alt="Profil"
          class="w-full max-w-[320px] sm:max-w-[420px] md:max-w-[520px] lg:max-w-[616px] h-auto object-cover rounded-lg"
        />
      </div>
    </div>

    <div class="mt-16">
      <FacilityHighlight />
    </div>
  </section>
</template>

<script setup lang="ts">
import profileImg from '@/assets/images/sections/profile.png'
import StatsHighlight from './StatsHighlight.vue'
import FacilityHighlight from './FacilityHighlight.vue'
import Badge from '@/components/Badge.vue'
</script>
