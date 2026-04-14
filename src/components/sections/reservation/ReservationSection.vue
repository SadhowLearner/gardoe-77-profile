<template>
  <section id="pemesanan" class="px-8 md:px-16 lg:px-20">
    <div class="w-full flex flex-col gap-4 md:gap-6 items-center md:items-start">
      <Badge>Pemesanan</Badge>

      <div
        class="w-full text-center md:text-justify flex flex-col lg:flex-row items-center lg:items-end justify-between gap-6 lg:gap-x-20"
      >
        <h2 class="text-3xl sm:text-4xl md:text-5xl leading-tight md:leading-[1.2] font-semibold">
          Reservasi Mudah, <br class="hidden sm:block" />
          Nongkrong Jadi Nyaman
        </h2>

        <h4 class="text-sm sm:text-base md:text-lg max-w-md leading-relaxed">
          Nikmati suasana nyaman di Gardoe77 Pakisadji. <br class="hidden sm:block" />
          Reservasi mudah melalui form atau WhatsApp.
        </h4>
      </div>
    </div>

    <div
      class="grid grid-cols-5 gap-14 bg-[#F9F8F5]/20 rounded-2xl md:rounded-[34px] w-full mt-15 py-15 px-13"
    >
      <FieldGroup class="col-span-5 gap-y-12.5 lg:col-span-3 w-full h-full">
        <div class="flex flex-col md:flex-row gap-y-12.5 gap-x-20">
          <Field>
            <FieldLabel for="name">
              <h4 class="font-medium!">Nama :</h4>
            </FieldLabel>
            <Input id="name" class="mt-2.25" v-model="form.name" />
          </Field>
          <Field>
            <FieldLabel for="telp">
              <h4 class="font-medium!">Nomor Whatsapp :</h4>
            </FieldLabel>
            <Input id="telp" class="mt-2.25" v-model="form.telp" />
          </Field>
        </div>
        <Field>
          <FieldLabel for="reservation-date">
            <h4 class="font-medium!">Tanggal Reservasi Acara :</h4>
          </FieldLabel>
          <Input id="reservation-date" v-model="form.date" />
        </Field>
        <Field>
          <FieldLabel for="number-of-people">
            <h4 class="font-medium!">Jumlah Orang :</h4>
          </FieldLabel>
          <Input id="number-of-people" v-model="form.people" />
        </Field>
        <Field>
          <FieldLabel for="notes">
            <h4 class="font-medium!">Catatan / Keperluan :</h4>
          </FieldLabel>
          <Input
            id="notes"
            placeholder="(Nongkrong, Meeting, Gathering, Ulang Tahun, dll)"
            v-model="form.notes"
          />
        </Field>
        <div class="flex gap-4 mx-auto lg:ms-0">
          <Button as-child variant="default" class="bg-white/20 px-6! py-5!"
            ><a class="text-white text-lg!" :href="waLink"> Kirim </a></Button
          >
        </div>
      </FieldGroup>
      <FAQ />
    </div>
  </section>
</template>

<script setup lang="ts">
import Badge from '@/components/Badge.vue'
import FAQ from './FAQ.vue'
import { Field, FieldGroup, FieldLabel } from '@/components/ui/field'
import { Input } from '@/components/ui/input'
import { Button } from '@/components/ui/button'

import { reactive, computed } from 'vue'

const form = reactive({
  name: '',
  telp: '',
  date: '',
  people: '',
  notes: '',
})

const waLink = computed(() => {
  const message = `Halo, saya ingin reservasi:

Nama: ${form.name}
No WA: ${form.telp}
Tanggal: ${form.date}
Jumlah Orang: ${form.people}
Catatan: ${form.notes}`

  return `https://wa.me/6285700816852?text=${encodeURIComponent(message)}`
})
</script>

<style scoped></style>
