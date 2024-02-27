<script setup>
import Posts from "./components/naive/Posts.vue"
// import Posts from "./components/better/Posts.vue"
// import Posts from "./components/optimized/Posts.vue"
</script>

<template>
  <header class="is-flex is-justify-content-center">
    <h1>My Posts</h1>
  </header>
  <main style="margin-top: 1rem;"
        class="is-flex is-justify-content-center">
    <Posts />
  </main>
</template>
