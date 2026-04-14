<template>
  <section id="galeri" class="flex flex-col px-8 md:px-16 lg:px-20">
    <div
      class="flex flex-col items-center text-center gap-4 md:gap-6 mb-10 md:mb-16 px-4 sm:px-8 md:px-12 lg:px-20"
    >
      <Badge>Galeri Gardoe77</Badge>

      <h2 class="text-3xl sm:text-4xl md:text-5xl font-semibold">Vibes Kedai Kami</h2>

      <h4 class="text-sm sm:text-base md:text-lg max-w-xl leading-relaxed">
        Intip suasana yang hangat dan klasik yang menanti anda
      </h4>
    </div>
    <div
      class="grid gap-4 md:gap-5 transition-all duration-700 ease-in-out grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 auto-rows-[200px] md:auto-rows-[250px]"
      :class="isExpanded ? '' : 'max-h-125 overflow-hidden'"
    >
      <!-- Baris pertama (selalu tampil) -->
      <img :src="img1" class="w-full h-full object-cover rounded-xl" />
      <img :src="img3" class="h-full object-cover rounded-xl w-full row-span-2" />
      <img :src="img4" class="w-full h-full object-cover rounded-xl" />
      <img :src="img2" class="w-full h-full object-cover rounded-xl" />
      <img :src="img5" class="w-full h-full object-cover rounded-xl" />

      <!-- Baris tambahan (muncul saat expand) -->
      <template v-if="isExpanded">
        <!-- Kolom kiri: img6 (row-span-2) + img7 (row-span-2) -->
        <img
          :src="img6"
          class="w-full h-full object-cover rounded-xl row-span-2 transition-all duration-700 ease-in-out"
        />

        <!-- Kolom tengah: img10 + img11 + img12 -->
        <div class="grid grid-rows-3 grid-cols-1 row-span-4 gap-5">
          <img
            :src="img10"
            class="w-full h-full object-cover rounded-xl transition-all duration-700 ease-in-out"
          />
          <img
            :src="img11"
            class="w-full h-full object-cover rounded-xl transition-all duration-700 ease-in-out"
          />
          <img
            :src="img12"
            class="w-full h-full object-cover rounded-xl transition-all duration-700 ease-in-out"
          />
        </div>
        <img
          :src="img8"
          class="w-full h-full object-cover rounded-xl row-span-2 transition-all duration-700 ease-in-out"
        />

        <img
          :src="img7"
          class="w-full h-full object-cover rounded-xl row-span-2 transition-all duration-700 ease-in-out"
        />

        <img
          :src="img9"
          class="w-full h-full object-cover rounded-xl row-span-2 transition-all duration-700 ease-in-out"
        />
      </template>
    </div>

    <Button
      @click="isExpanded = !isExpanded"
      class="mx-auto mt-16 text-foreground playfair-display font-medium text-xl! px-7 py-7 rounded-2xl transition-all duration-300"
    >
      {{ isExpanded ? 'Lihat Lebih Sedikit' : 'Lihat Lebih Banyak' }}
    </Button>
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
import img1 from '@/assets/images/gallery/1.png'
import img2 from '@/assets/images/gallery/2.png'
import img3 from '@/assets/images/gallery/3.png'
import img4 from '@/assets/images/gallery/4.png'
import img5 from '@/assets/images/gallery/5.png'

import img6 from '@/assets/images/gallery/6.png'
import img7 from '@/assets/images/gallery/7.png'
import img8 from '@/assets/images/gallery/8.png'
import img9 from '@/assets/images/gallery/9.png'
import img10 from '@/assets/images/gallery/10.png'
import img11 from '@/assets/images/gallery/11.png'
import img12 from '@/assets/images/gallery/12.png'

import { Button } from '@/components/ui/button'
import { ref } from 'vue'

const isExpanded = ref(false)
</script>
<style scoped>
img {
  animation: fadeIn 0.7s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(16px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
