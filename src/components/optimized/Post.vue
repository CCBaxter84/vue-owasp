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
    <h2 style="text-transform: uppercase;">{{ source.title }}</h2>
    <p>{{ source.body }}</p>
  </article>
</template>