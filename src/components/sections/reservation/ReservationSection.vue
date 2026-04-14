<template>
  <section id="pemesanan" class="px-20">
    <div class="w-full flex flex-col gap-5">
      <Badge> Pemesanan </Badge>
      <div class="flex w-full items-end justify-between gap-x-28.5">
        <h2 class="leading-16 text-5xl">
          Reservasi Mudah, <br />
          Nongkrong Jadi Nyaman
        </h2>
        <h4>
          Nikmati suasana nyaman di Gardoe77 Pakisadji. <br />
          Reservasi mudah melalui form atau WhatsApp.
        </h4>
      </div>
    </div>

    <div class="grid grid-cols-5 gap-x-14 bg-[#F9F8F5]/20 rounded-[34px] w-full mt-15 py-15 px-13">
      <FieldGroup class="col-span-5 gap-y-12.5 md:col-span-3 w-full h-full">
        <div class="flex gap-x-20">
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
            <Input id="telp" v-model="form.telp" />
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
        <div class="flex gap-4">
          <Button as-child variant="default" class="bg-white/20"
            ><a class="text-white" :href="waLink"> Kirim </a></Button
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
