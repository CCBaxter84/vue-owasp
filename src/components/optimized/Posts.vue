<script setup>
import VirtualList from "vue3-virtual-scroll-list"
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
  <VirtualList  v-if="hasPosts"
                :dataSources="posts"
                :dataComponent="Post"
                dataKey="id"
                wrapTag="section"
                style="max-height: 85vh; 
                  overflow-y: auto; 
                  scrollbar-color: var(--text-color) transparent;
                  scrollbar-width: thin"/>
  <section  v-else>
    <article>
      <p>Loading ...</p>
    </article>
  </section>
</template>