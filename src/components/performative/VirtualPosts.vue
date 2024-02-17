<script setup>
import VirtualList from "vue3-virtual-scroll-list"
import { ref, onMounted, computed } from "vue"
import DummyPost from "./DummyPost.vue"

const posts = ref([])
const hasPosts = computed(() => {
  return !!(posts.value.length)
})

onMounted(async() => {
  const res = await fetch("https://jsonplaceholder.typicode.com/posts")
  const initialPosts = await res.json()
  posts.value = initialPosts.map(post => {
    return { 
      ...post, 
      title: post.title.toUpperCase() 
    }
  })
})
</script>

<template>
  <section>
    <template v-if="hasPosts">
    <VirtualList  :dataSources="posts"
                  :dataComponent="DummyPost"
                  :keeps="50"
                  dataKey="id"/>
    </template>
    <p  v-else>Loading ...</p>
  </section>
</template>