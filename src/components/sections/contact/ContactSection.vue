<template>
  <section id="lokasi" class="px-20">
    <div class="flex flex-col justify-center w-full items-center gap-7 mb-16!">
      <Badge> Lokasi & Kontak Kami </Badge>
      <h2 class="text-5xl">Butuh Bantuan ? Hubungi Kami</h2>
      <h4>Kami siap melayani pemesanan online maupun langsung.</h4>
    </div>
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3950.3139591883523!2d112.5957634760003!3d-8.069424891958468!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e789d6bf886a22d%3A0x46635d1df22a12fd!2sGardoe77!5e0!3m2!1sid!2sid!4v1775570607798!5m2!1sid!2sid"
      class="w-full rounded-2xl"
      height="617"
      style="border: 0"
      allowfullscreen
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
    ></iframe>
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
</script>

<style scoped></style>
