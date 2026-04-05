<template>
  <ul class="w-109 flex flex-col gap-3" :class="props.class">
    <li v-for="item in menu" class="w-full text-start">
      <h5 class="-mb-3">{{ item.name }}</h5>
      <div class="flex max-w-full w-full justify-start items-baseline gap-2">
        <p class="min-w-max w-max text-base!">{{ item.contents }}</p>
        <Separator decorative class="grow! min-w-0" />
        <h5 class="min-w-max">{{ item.price }}</h5>
      </div>
    </li>
  </ul>
</template>

<script setup lang="ts">
import { Separator } from '@/components/ui/separator'
import type { ClassValue } from 'clsx'
import type { HTMLAttributes } from 'vue'

type menuItem = {
  name: string
  contents: string
  price: string
}
const props = defineProps<{ menu: menuItem[]; class?: string }>()
</script>
