<template>
  <section class="px-20">
    <Badge> Menu Favorit </Badge>
    <h2 class="text-5xl mt-5 leading-16">
      Menu Andalan <br />
      yang Paling Disukai
    </h2>
    <h4 class="mt-5 leading-8 mb-15.5">
      Berbagai hidangan dan minuman favorit yang menghadirkan rasa nikmat untuk menemani waktu
      bersantai.
    </h4>
    <CardMenu :menu="menu" />
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
import kopi from '@/assets/images/favorites/kopi.png'
import katshu from '@/assets/images/favorites/katshu.png'
import cappucino from '@/assets/images/favorites/cappucino.png'
import cireng from '@/assets/images/favorites/cireng.png'
import kopiAren from '@/assets/images/favorites/eskopiaren.png'
import esKopiGardoe from '@/assets/images/favorites/eskopigardoe.png'
import unionRing from '@/assets/images/favorites/onionring.png'
import pinkBu from '@/assets/images/favorites/pinkbu.png'
import rotiIceBakar from '@/assets/images/favorites/rotiicebakar.png'
import tahuTelor from '@/assets/images/favorites/tahutelor.png'
import mendoan from '@/assets/images/favorites/tempemendoan.png'
import tubrukSusu from '@/assets/images/favorites/tubruksusu.png'
import CardMenu from './CardMenu.vue'

const menu = [
  {
    image: kopi,
    name: 'Tubruk Gardoe',
    contents: 'Biji robusta + biji sidomukti giras',
    price: '12.00',
  },
  {
    image: tubrukSusu,
    name: 'Tubruk Susu',
    contents: 'Tubruk gardoe + susu',
    price: '13.00',
  },
  {
    image: kopiAren,
    name: 'Es Kopi Gula Aren',
    contents: 'Sirup gula aren + susu + kopi',
    price: '17.50',
  },
  {
    image: cappucino,
    name: 'Cappucino Gardoe77',
    contents: 'Teh + Gula + sirup',
    price: '18.00',
  },
  {
    image: pinkBu,
    name: 'Pink Bu',
    contents: 'Sirup strawberry + susu + oreo crus',
    price: '17.00',
  },
  {
    image: esKopiGardoe,
    name: 'Es Kopi Gardoe',
    contents: 'Sirup caramel + susu + kopi',
    price: '15.50',
  },
  {
    image: rotiIceBakar,
    name: 'Roti Bakar Ice Bakar',
    contents: 'Roti Bakar + Ice Cream',
    price: '17.50',
  },
  {
    image: katshu,
    name: 'Chicken Katshu',
    contents: 'Ayam Katshu + nasi + saos',
    price: '19.50',
  },
  {
    image: cireng,
    name: 'Cireng Goreng',
    contents: 'Cireng goreng + Bumbu rujak',
    price: '12.50',
  },
  {
    image: unionRing,
    name: 'Union Ring',
    contents: 'Bawang bombay + saos',
    price: '16.50',
  },
  {
    image: mendoan,
    name: 'Tempe Mendoan',
    contents: 'Tempe mendoan + saos',
    price: '12.50',
  },
  {
    image: tahuTelor,
    name: 'Tahu Telor Gardoe',
    contents: 'Tahu telor + nasi + bumbu + krupuk',
    price: '15.50',
  },
]
</script>
