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
  <VirtualList  v-if="hasPosts"
                :dataSources="posts"
                :dataComponent="Post"
                dataKey="id"
                wrapTag="section"
                style="max-height: 85vh; 
                  overflow-y: auto; 
                  scrollbar-color: aliceblue transparent;
                  scrollbar-width: thin"
                itemTag="article"
                itemClass="is-flex is-flex-direction-column"
                itemStyle="margin: 1rem 2rem;"/>
  <section  v-else>
    <article>
      <p>Loading ...</p>
    </article>
  </section>
</template>