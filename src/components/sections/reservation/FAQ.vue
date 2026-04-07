<template>
  <div class="col-span-5 md:col-span-2 gap-9 flex flex-col">
    <div>
      <h3 class="text-[30px] leading-[140%]! pb-2">
        Pertanyaan Camper <br />
        yang Sering Diajukan!
      </h3>
      <h4 class="font-light!">Informasi cepat sebelum kamu ketempat!</h4>
    </div>
    <Accordion type="multiple" collapsible class="">
      <AccordionItem
        v-for="(item, key) in items"
        :key="key"
        :value="item.question"
        class="bg-white/20 px-5 border border-white/10 rounded-2xl mt-7"
      >
        <AccordionTrigger>
          <h4>{{ item.question }}</h4>
        </AccordionTrigger>
        <AccordionContent class="font-light text-sm">
          {{ item.answer }}
        </AccordionContent>
      </AccordionItem>
    </Accordion>
  </div>
</template>

<script setup lang="ts">
import {
  Accordion,
  AccordionItem,
  AccordionContent,
  AccordionTrigger,
} from '@/components/ui/accordion'

const items = [
  {
    question: 'Gardoe77 menyediakan fasilitas AC?',
    answer:
      'Gardoe77 tidak menyediakan fasilitas AC. Namun, suasana tetap nyaman dengan sirkulasi udara yang baik.',
  },
  {
    question: 'Bisa reservasi untuk acara kecil?',
    answer:
      'Iya, Reservasi tersedia untuk acara kecil seperti perayaan ulang tahun anak- anak dll. Silakan hubungi kami.',
  },
  {
    question: 'Apakah bisa bayar pakai qris?',
    answer:
      'Pembayaran dapat dilakukan menggunakan QRIS. Praktis dan memudahkan transaksi tanpa uang tunai.',
  },
  {
    question: 'Kebijakan kunjungan tanpa reservasi',
    answer:
      'Pengunjung dapat datang langsung tanpa reservasi. Ketersediaan tempat menyesuaikan kondisi saat itu.',
  },
]
</script>
