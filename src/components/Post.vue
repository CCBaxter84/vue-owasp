<script setup>
import { computed } from "vue"
const props = defineProps({
  post: {
    type: Object,
    required: true
  }
})
const title = computed(() => {
  return props.post.title.toUpperCase()
})
</script>

<template>
  <article  style="margin: 1rem 2rem;"
            class="is-flex is-flex-direction-column">
    <h2>{{ title }}</h2>
    <p>{{ props.post.body }}</p>
  </article>
</template>