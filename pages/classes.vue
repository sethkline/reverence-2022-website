<template>
  <StoryblokComponent v-if="story" :blok="story.content" />
</template>

<script setup lang="ts">
const story = await useStoryblok('/classes', { version: 'draft' })

</script>