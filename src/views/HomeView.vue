<script setup>
import PostService from '@/services/PostService'
import { ref, onMounted } from 'vue'

const service = new PostService()
const posts = service.getPosts()

onMounted(async () => {
  await service.fetchAll()
})

console.log(posts)
</script>

<template>
  <ul>
    <li v-for="post in posts" :key="post.id">
      {{ post.title }}
    </li>
  </ul>
</template>
