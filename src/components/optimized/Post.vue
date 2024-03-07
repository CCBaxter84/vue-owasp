<script setup>
defineProps({
  source: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <article  style="margin: 1rem 2rem;"
            class="is-flex is-flex-direction-column">
    <h2>{{ source.title }}</h2>
    <p>{{ source.body }}</p>
  </article>
</template>