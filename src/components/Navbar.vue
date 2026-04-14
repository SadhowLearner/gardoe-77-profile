<template>
  <div
    class="flex items-center justify-between mx-auto mt-8 px-6 rounded-lg w-9/10 bg-white/20 backdrop-blur-md border border-white/10 shadow-lg"
  >
    <!-- Logo -->
    <img :src="gardoe77" class="text-white font-semibold" />

    <!-- NavigationMenu -->
    <NavigationMenu>
      <NavigationMenuList class="flex gap-8">
        <NavigationMenuItem v-for="item in navItems" :key="item.id">
          <NavigationMenuLink as-child>
            <Button
              variant="ghost"
              @click="scrollTo(item.id)"
              :class="[
                'text-sm transition',
                activeSection === item.id
                  ? 'text-orange-400 bg-transparent'
                  : 'text-white/70 hover:text-white',
              ]"
            >
              {{ item.label }}
            </Button>
          </NavigationMenuLink>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>

    <!-- Right -->
    <Button variant="ghost" @click="scrollTo('contact')" class="text-white hover:text-orange-400">
      Kontak
      <ArrowUpRight color="currentColor" stroke="currentColor" class="text-orange-400!" />
    </Button>
  </div>
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
import { ArrowUpRight } from 'lucide-vue-next'

const activeSection = ref('')

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
