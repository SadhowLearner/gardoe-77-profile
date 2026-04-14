<template>
  <section>
    <div
      class="flex flex-col items-center text-center gap-4 md:gap-6 px-4 sm:px-8 md:px-12 lg:px-20 mb-10 md:mb-16"
    >
      <Badge>Apa Kata Mereka</Badge>

      <h2 class="text-3xl sm:text-4xl md:text-5xl font-semibold">Gardoe & Pelanggan</h2>

      <h4 class="text-sm sm:text-base md:text-lg max-w-xl md:max-w-2xl leading-relaxed">
        Lihat kesan dan cerita dari pelanggan yang pernah berkunjung. <br class="hidden sm:block" />
        Nikmati suasana hangat dan menu favorit di Gardoe77 Pakisadji.
      </h4>
    </div>
    <TestimonialCards :testimoni="testimonials" />
  </section>
</template>

<script setup lang="ts">
import TestimonialCards from './TestimonialCards.vue'

import img1 from '@/assets/images/profiles/1.png'
import img2 from '@/assets/images/profiles/2.png'
import img3 from '@/assets/images/profiles/3.png'
import img4 from '@/assets/images/profiles/4.png'
import img5 from '@/assets/images/profiles/5.png'
import img6 from '@/assets/images/profiles/6.png'
import rating4 from '@/assets/images/icons/rating4.svg'
import rating3 from '@/assets/images/icons/rating3.svg'
import Badge from '@/components/Badge.vue'

const testimonials = [
  {
    testimoni:
      'Cafe dengan suasana vintage dan asri di samping Stasiun Pakisaji. Bisa lihat kereta berlalu lalang karena letaknya persis di sebelah stasiun.',
    name: 'Kurniawan Sakti',
    title: 'Pengusaha Barang Antik',
    profile: img1,
  },
  {
    testimoni:
      'Suka dengan makanan ringan dan kopinya. Cocok di lidah, tempatnya juga bagus, adem, dan nyaman. Cocok buat kumpul dengan keluarga atau teman.',
    name: 'Putra Maheswara',
    title: 'Anak Rajin',
    profile: img2,
  },
  {
    testimoni:
      'Suasana tenang dan cocok untuk menghabiskan waktu bersama teman dan keluarga. Harganya terjangkau dan lokasi mudah dijangkau.',
    name: 'Nurul Istatik Putri',
    title: 'Ibuk Paling Sabar',
    profile: img3,
  },
  {
    testimoni:
      'Tempat nyaman untuk ngopi, nongkrong, atau bersama keluarga dengan suasana cozy. Harga terjangkau, dan tersedia board game, meski tutup cukup cepat.',
    name: 'Budi Prasetyo',
    title: 'Pecinta Nongkrong',
    profile: img4,
  },
  {
    testimoni:
      'Kopi susu Gardoe recommended banget, makanannya juga lumayan enak. Tapi kucingnya dikandangin aja pliss..',
    name: 'Nur Aisyah',
    title: 'Mahasiswi Perkantoran',
    profile: img5,
    rating: rating4,
  },
  {
    testimoni:
      'Harga terjangkau, parkir gratis, lokasi mudah, WiFi cepat, dan tersedia stop kontak. Namun, pelayanan kurang sigap, kebersihan perlu ditingkatkan, serta pesanan agak terlambat.',
    name: 'Nandyan Ayu',
    title: 'Pecinta Kebersihan',
    profile: img6,
    rating: rating3,
  },
]
</script>

<style scoped></style>
