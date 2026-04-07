<template>
  <ScrollArea class="w-full pt-0! whitespace-nowrap rounded-2xl">
    <div
      ref="scrollRef"
      class="overflow-x-auto overflow-y-hidden cursor-grab active:cursor-grabbing scroll-smooth select-none"
      @mousedown="startDrag"
      @mousemove="onDrag"
      @mouseleave="stopDrag"
    >
      <div class="grid grid-rows-2 grid-cols-6 gap-8 w-max pb-4">
        <Card
          v-for="item in menu"
          :key="item.name"
          class="p-4! bg-white/20 border-0 shrink-0 rounded-2xl"
        >
          <CardHeader class="relative w-full p-0">
            <img
              :src="item.image"
              :alt="item.name"
              class="object-content w-full"
              draggable="false"
            />
          </CardHeader>

          <CardContent class="space-y-2 p-0">
            <div class="flex items-start">
              <p class="text-xl! text-primary! font-medium! border-b border-white/50 flex-1 grow">
                {{ item.name }}
              </p>
              <p class="text-xl! text-primary! font-medium! whitespace-nowrap">
                {{ item.price }}
              </p>
            </div>

            <p class="text-accent text-sm! font-light leading-relaxed">
              {{ item.contents }}
            </p>
          </CardContent>
        </Card>
      </div>
    </div>

    <ScrollBar orientation="horizontal" />
  </ScrollArea>
</template>

<script setup lang="ts">
import { Card, CardContent, CardHeader } from '@/components/ui/card'
import { ScrollArea } from '@/components/ui/scroll-area'

const props = defineProps<{
  menu: {
    image: string
    name: string
    contents: string
    price: string
  }[]
}>()

import { ref, onMounted, onBeforeUnmount } from 'vue'

const scrollRef = ref<HTMLElement | null>(null)

let isDown = false
let startX = 0
let scrollLeft = 0

const startDrag = (e: MouseEvent) => {
  if (!scrollRef.value) return

  isDown = true
  startX = e.pageX - scrollRef.value.offsetLeft
  scrollLeft = scrollRef.value.scrollLeft
}

const stopDrag = () => {
  isDown = false
}

const onDrag = (e: MouseEvent) => {
  if (!isDown || !scrollRef.value) return

  e.preventDefault()
  const x = e.pageX - scrollRef.value.offsetLeft
  const walk = (x - startX) * 1 // makin besar makin cepat
  scrollRef.value.scrollLeft = scrollLeft - walk
}

onMounted(() => {
  window.addEventListener('mouseup', stopDrag)
})

onBeforeUnmount(() => {
  window.removeEventListener('mouseup', stopDrag)
})
</script>
