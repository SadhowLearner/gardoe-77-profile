<template>
  <div class="pt-12">
    <!-- WRAPPER LUAR (AMAN DARI CLIP) -->
    <div class="relative overflow-visible">
      <!-- SCROLL AREA -->
      <div
        ref="scrollRef"
        class="overflow-x-auto overflow-y-hidden cursor-grab active:cursor-grabbing select-none pb-8 scrollbar-hide"
        @mousedown="startDrag"
        @mousemove="onDrag"
        @mouseleave="stopDrag"
        @mouseup="stopDrag"
      >
        <div class="flex gap-8 w-max">
          <div
            v-for="(item, index) in loopMenu"
            :key="`${item.name}-${index}`"
            class="relative pt-12 shrink-0"
          >
            <!-- Icon Quote -->
            <img
              class="absolute left-1/2 top-0 -translate-x-1/2 translate-y-5 z-20 w-6 sm:w-7 md:w-auto"
              :src="testimoni"
              alt="Quote"
            />

            <!-- CARD -->
            <Card
              class="w-[260px] sm:w-[320px] md:w-[420px] lg:w-[615px] min-w-[260px] sm:min-w-[320px] md:min-w-[420px] lg:min-w-[615px] h-[339px] p-6 sm:p-8 md:p-10 lg:p-12 py-8 sm:py-12 md:py-14 lg:py-16 h-full bg-[#FDFDFD] border-0 rounded-2xl"
            >
              <CardContent class="flex flex-col items-center h-full p-0 gap-6 md:gap-8">
                <!-- Rating -->
                <h4
                  class="font-normal! text-sm! sm:text-base! md:text-lg! playfair-display text-[#522705]! text-center flex-1"
                >
                  {{ item.testimoni }}
                </h4>
                <img
                  :src="item.rating ?? rating"
                  alt="Rating"
                  class="w-20 sm:w-24 md:w-auto mx-auto"
                />

                <!-- Profile -->
                <div class="flex items-center gap-3 sm:gap-4 mt-auto">
                  <img
                    :src="item.profile"
                    :alt="item.name"
                    class="w-10 h-10 sm:w-12 sm:h-12 md:w-14 md:h-14"
                  />

                  <div>
                    <h5
                      class="work-sans text-sm! sm:text-base! md:text-lg! font-semibold! leading-none text-[#522705]!"
                    >
                      {{ item.name }}
                    </h5>

                    <p
                      class="work-sans text-xs! sm:text-sm! md:text-base! font-light text-[#522705]!"
                    >
                      {{ item.title }}
                    </p>
                  </div>
                </div>
              </CardContent>
            </Card>
          </div>
        </div>
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

// LOOP DATA (tetap infinite)
const loopMenu = computed(() => {
  return [...props.testimoni, ...props.testimoni, ...props.testimoni]
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
    scrollRef.value.scrollLeft = oneThird
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
