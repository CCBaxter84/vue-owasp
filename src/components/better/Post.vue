<script setup>
defineProps({
  post: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <article  style="margin: 1rem 2rem;"
            class="is-flex is-flex-direction-column">
    <h2>{{ post.title }}</h2>
    <p>{{ post.body }}</p>
  </article>
</template>