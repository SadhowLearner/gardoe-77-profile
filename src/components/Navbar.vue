<script setup lang="ts">
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuIndicator,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle,
  NavigationMenuViewport,
} from '@/components/ui/navigation-menu'

import gardoe77 from '@assets/images/gardoe77.png'
</script>

<template>
  <NavigationMenu class="w-3/5 bg-[#FFFAFA]">
    <NavigationMenuList class="flex gap-14 items-baseline pb-16">
      <NavigationMenuItem>
        <NavigationMenuLink as-child :class="navigationMenuTriggerStyle">
          <a href="/">Profil Kami</a>
        </NavigationMenuLink>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuLink as-child :class="navigationMenuTriggerStyle">
          <a href="/">Galeri</a>
        </NavigationMenuLink>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <img :src="gardoe77" alt="" class="w-26.5 translate-y-4" />
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuLink as-child :class="navigationMenuTriggerStyle">
          <a href="/">Pemesanan</a>
        </NavigationMenuLink>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuLink as-child :class="navigationMenuTriggerStyle">
          <a href="/">Lokasi</a>
        </NavigationMenuLink>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
