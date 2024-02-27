<script setup>
const props = defineProps({
  source: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <h2>{{ props.source.title }}</h2>
  <p>{{ props.source.body }}</p>
</template>