<template>
  <div
    v-editable="blok"
    class="py-32 text-6xl text-[#50b0ae] font-bold text-center"
  >
    {{ blok.headline }}
  </div>
</template>

<script setup lang="ts">
import type { SbBlokData } from '@storyblok/js'
export interface SbComponentProps {
      blok: SbBlokData
    }
defineProps<SbComponentProps>()
</script>