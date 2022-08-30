<template>
  <div v-editable="blok" class="font-[Roboto] px-4">
    <StoryblokComponent
      v-for="blok in blok.body"
      :key="blok._uid"
      :blok="blok"
    />
  </div>
</template>

<script setup lang="ts">
import type { SbBlokData } from '@storyblok/js'
export interface SbComponentProps {
      blok: SbBlokData
    }
defineProps<SbComponentProps>()
</script>
