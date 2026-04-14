<script setup lang="ts">
import type { TabsTriggerProps } from 'reka-ui'
import type { HTMLAttributes } from 'vue'
import { reactiveOmit } from '@vueuse/core'
import { TabsTrigger, useForwardProps } from 'reka-ui'
import { cn } from '@/lib/utils'

const props = defineProps<TabsTriggerProps & { class?: HTMLAttributes['class'] }>()

const delegatedProps = reactiveOmit(props, 'class')

const forwardedProps = useForwardProps(delegatedProps)
</script>

<template>
  <TabsTrigger
    data-slot="tabs-trigger"
    :class="
      cn(
        // ACTIVE STATE
        'data-[state=active]:bg-primary data-[state=active]:shadow-sm',

        // TEXT
        'text-foreground dark:text-muted-foreground',
        '[&[data-state=active]_*]:text-secondary',

        // LAYOUT
        'inline-flex items-center justify-center gap-1.5',
        'rounded-xl md:rounded-2xl flex-1',

        // SIZE (responsive)
        'px-3 py-1 text-xs',
        'sm:px-4 sm:text-sm',
        'md:px-5 md:py-1.5',

        // IMPORTANT: jangan pakai flex-1
        'w-auto shrink-0',

        // BEHAVIOR
        'transition whitespace-nowrap',

        // FOCUS
        'focus-visible:ring-2 focus-visible:ring-ring/50',

        // DISABLED
        'disabled:pointer-events-none disabled:opacity-50',

        props.class,
      )
    "
    v-bind="forwardedProps"
  >
    <slot />
  </TabsTrigger>
</template>
