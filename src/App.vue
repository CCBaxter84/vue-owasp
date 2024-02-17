<script setup>
// import Posts from "./components/Posts.vue"
import VirtualPosts from "./components/performative/VirtualPosts.vue"
</script>

<template>
  <header class="is-flex is-justify-content-center">
    <h1>My Posts</h1>
  </header>
  <main   style="margin-top: 1rem;"
          class="is-flex is-justify-content-center">
    <VirtualPosts />
  </main>
</template>d
