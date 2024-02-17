<script setup>
import { computed } from "vue"
const props = defineProps({
  source: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <article  style="margin: 1rem 2rem;"
            class="is-flex is-flex-direction-column">
    <h2>{{ props.source.title }}</h2>
    <p>{{ props.source.body }}</p>
  </article>
</template>