<script setup>
import { ref, onMounted, computed } from "vue"
import Post from "./Post.vue"

const posts = ref([])
const hasPosts = computed(() => {
  return !!(posts.value.length)
})

onMounted(async() => {
  const res = await fetch("https://jsonplaceholder.typicode.com/posts")
  posts.value = await res.json()
})
</script>

<template>
  <section>
    <template v-if="hasPosts">
      <Post v-for="post in posts"
            :key="post.id"
            :post="post"/>
    </template>
    <p v-else>Loading ...</p>
  </section>
</template>