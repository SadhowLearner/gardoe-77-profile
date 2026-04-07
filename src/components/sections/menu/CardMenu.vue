<template>
  <div
    ref="scrollRef"
    class="overflow-x-auto overflow-y-hidden cursor-grab active:cursor-grabbing select-none pb-4 scrollbar-hide"
    @mousedown="startDrag"
    @mousemove="onDrag"
    @mouseleave="stopDrag"
    @mouseup="stopDrag"
  >
    <div
      class="grid grid-rows-2 gap-8 w-max"
      :style="{ gridTemplateColumns: `repeat(${loopMenu.length / 2}, 18.25rem)` }"
    >
      <Card
        v-for="(item, index) in loopMenu"
        :key="`${item.name}-${index}`"
        class="p-4! bg-white/20 border-0 shrink-0 rounded-2xl min-w-73"
      >
        <CardHeader class="relative w-full p-0">
          <img :src="item.image" :alt="item.name" class="object-cover w-full" draggable="false" />
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
</template>

<script setup lang="ts">
import { Card, CardContent, CardHeader } from '@/components/ui/card'
import { ref, onMounted, onBeforeUnmount, computed } from 'vue'

const props = defineProps<{
  menu: {
    image: string
    name: string
    contents: string
    price: string
  }[]
}>()

// Duplikat 3x, pastikan jumlah item selalu genap untuk grid-rows-2
const loopMenu = computed(() => {
  const tripled = [...props.menu, ...props.menu, ...props.menu]
  // Pastikan genap agar grid 2 baris rapi
  return tripled.length % 2 === 0 ? tripled : [...tripled, tripled[0]]
})

const scrollRef = ref<HTMLElement | null>(null)
let animationFrame: number
let isDragging = false

const SCROLL_SPEED = 0.5

const autoScroll = () => {
  if (!scrollRef.value || isDragging) {
    animationFrame = requestAnimationFrame(autoScroll)
    return
  }

  scrollRef.value.scrollLeft += SCROLL_SPEED

  const totalWidth = scrollRef.value.scrollWidth
  const oneThird = totalWidth / 3

  if (scrollRef.value.scrollLeft >= oneThird * 2) {
    scrollRef.value.scrollLeft -= oneThird
  }

  animationFrame = requestAnimationFrame(autoScroll)
}

let startX = 0
let scrollLeftStart = 0

const startDrag = (e: MouseEvent) => {
  if (!scrollRef.value) return
  isDragging = true
  startX = e.pageX - scrollRef.value.offsetLeft
  scrollLeftStart = scrollRef.value.scrollLeft
}

const stopDrag = () => {
  isDragging = false
}

const onDrag = (e: MouseEvent) => {
  if (!isDragging || !scrollRef.value) return
  e.preventDefault()
  const x = e.pageX - scrollRef.value.offsetLeft
  const walk = (x - startX) * 1.2
  scrollRef.value.scrollLeft = scrollLeftStart - walk

  const totalWidth = scrollRef.value.scrollWidth
  const oneThird = totalWidth / 3
  if (scrollRef.value.scrollLeft < 0) {
    scrollRef.value.scrollLeft += oneThird
    scrollLeftStart += oneThird
  } else if (scrollRef.value.scrollLeft >= oneThird * 2) {
    scrollRef.value.scrollLeft -= oneThird
    scrollLeftStart -= oneThird
  }
}

onMounted(() => {
  window.addEventListener('mouseup', stopDrag)

  if (scrollRef.value) {
    const oneThird = scrollRef.value.scrollWidth / 3
    scrollRef.value.scrollLeft = oneThird * 0.5
  }

  autoScroll()
})

onBeforeUnmount(() => {
  window.removeEventListener('mouseup', stopDrag)
  cancelAnimationFrame(animationFrame)
})
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
