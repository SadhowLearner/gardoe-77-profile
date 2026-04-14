<template>
  <div
    class="mx-auto mt-8 w-[95%] sm:w-[90%] lg:w-[85%] flex items-center justify-between px-4 sm:px-6 py-3 rounded-xl bg-white/20 backdrop-blur-md border border-white/10 shadow-lg"
  >
    <!-- Logo -->
    <img :src="gardoe77" class="h-8 sm:h-10" />

    <!-- Desktop Menu -->
    <NavigationMenu class="hidden lg:block">
      <NavigationMenuList class="flex justify-center gap-6">
        <NavigationMenuItem v-for="item in navItems" :key="item.id">
          <NavigationMenuLink as-child>
            <Button
              variant="ghost"
              @click="scrollTo(item.id)"
              :class="[
                'text-sm transition',
                activeSection === item.id ? 'text-orange-400' : 'text-white/70 hover:text-white',
              ]"
            >
              {{ item.label }}
            </Button>
          </NavigationMenuLink>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>

    <!-- Right (desktop) -->
    <div class="hidden lg:flex items-center gap-2">
      <Button variant="ghost" @click="scrollTo('contact')" class="text-white hover:text-orange-400">
        Kontak
        <ArrowUpRight class="ml-1 text-orange-400!" />
      </Button>
    </div>

    <!-- Mobile Menu Button -->
    <Button variant="ghost" class="lg:hidden text-white" @click="isOpen = !isOpen"
      ><Menu class="size-5"
    /></Button>
  </div>

  <!-- Mobile Dropdown -->
  <Sheet v-model:open="isOpen">
    <!-- <SheetTrigger as-child>
      <Button variant="ghost" class="lg:hidden"><Menu /></Button>
    </SheetTrigger> -->

    <SheetContent side="right" class="bg-black/90 pt-8 border-white/10">
      <div class="flex flex-col gap-4 mt-6 px-4">
        <Button
          v-for="item in navItems"
          :key="item.id"
          variant="ghost"
          class="justify-start text-white"
          @click="handleNavClick(item.id)"
        >
          {{ item.label }}
        </Button>
        <Button
          variant="ghost"
          @click="scrollTo('contact')"
          class="text-white justify-start pl-4! hover:text-orange-400"
        >
          Kontak
          <ArrowUpRight class="ml-1 text-orange-400" />
        </Button>
      </div>
    </SheetContent>
  </Sheet>
</template>

<script setup lang="ts">
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuList,
  NavigationMenuLink,
} from '@/components/ui/navigation-menu'

import { ref, onMounted, onBeforeUnmount } from 'vue'

import gardoe77 from '@/assets/images/icons/gardoe77.svg'
import { Button } from './ui/button'
import { ArrowUpRight, Menu } from 'lucide-vue-next'
import { Sheet, SheetContent, SheetTrigger } from './ui/sheet'

const activeSection = ref('')

const isOpen = ref(false)

const handleNavClick = (id: string) => {
  scrollTo(id)
  isOpen.value = false
}

const navItems = [
  { id: 'profil', label: 'Profil Kami' },
  { id: 'galeri', label: 'Galeri' },
  { id: 'pemesanan', label: 'Pemesanan' },
  { id: 'lokasi', label: 'Lokasi' },
]

const scrollTo = (id: string) => {
  const el = document.getElementById(id)
  if (!el) return

  el.scrollIntoView({
    behavior: 'smooth',
    block: 'start',
  })
}

// 🔥 versi lebih akurat pakai offset navbar
const handleScroll = () => {
  const offset = 140

  for (const item of navItems) {
    const el = document.getElementById(item.id)
    if (!el) continue

    const rect = el.getBoundingClientRect()

    if (rect.top <= offset && rect.bottom >= offset) {
      activeSection.value = item.id
      return
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
