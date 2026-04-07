<template>
  <div class="overflow-visible pt-12">
    <div
      ref="scrollRef"
      class="overflow-x-auto overflow-y-auto cursor-grab active:cursor-grabbing select-none pb-4 scrollbar-hide"
      @mousedown="startDrag"
      @mousemove="onDrag"
      @mouseleave="stopDrag"
      @mouseup="stopDrag"
    >
      <div
        class="grid grid-rows-1 gap-8 w-max"
        :style="{ gridTemplateColumns: `repeat(${loopMenu.length}, 38.43rem)` }"
      >
        <Card
          v-for="(item, index) in loopMenu"
          :key="`${item.name}-${index}`"
          class="p-13! py-16 w-153.75 bg-[#FDFDFD] border-0 relative shrink-0 rounded-2xl min-w-152.75 overflow-visible!"
        >
          <img class="absolute left-1/2 -translate-x-1/2 -top-8" :src="testimoni" alt="Quote" />
          <CardHeader class="w-full p-0">
            <h4 class="font-normal! text-lg! text-[#522705]! text-center">
              {{ item.testimoni }}
            </h4>
          </CardHeader>
          <CardContent class="flex flex-col items-center p-0 gap-8">
            <img :src="item.rating ?? rating" alt="Rating" />
            <div class="flex gap-4">
              <img :src="item.profile" :alt="item.name" class="w-14 h-13.5" />
              <div>
                <h5 class="work-sans! text-lg font-semibold! text-[#522705]!">{{ item.name }}</h5>
                <p class="work-sans! text-base! font-light! text-[#522705]!">{{ item.title }}</p>
              </div>
            </div>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Card, CardContent, CardHeader } from '@/components/ui/card'
import { ref, onMounted, onBeforeUnmount, computed } from 'vue'
import rating from '@/assets/images/icons/rating.svg'
import testimoni from '@/assets/images/icons/testimoni.svg'

const props = defineProps<{
  testimoni: {
    profile: string
    name: string
    title: string
    testimoni: string
    rating?: string
  }[]
}>()

// Duplikat 3x, pastikan jumlah item selalu genap untuk grid-rows-2
const loopMenu = computed(() => {
  return [...props.testimoni, ...props.testimoni]
  // Pastikan genap agar grid 2 baris rapi
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
