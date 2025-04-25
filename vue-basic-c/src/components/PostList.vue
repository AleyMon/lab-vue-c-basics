<script setup>
import { ref } from 'vue'

// Datos
const posts = ref([
  {
    title: 'Post 1',
    description: 'This is the first post description.',
    content: 'Content for the first post goes here.'
  },
  {
    title: 'Post 2',
    description: 'This is the second post description.',
    content: 'Content for the second post goes here.'
  }
])
</script>


<template>
    <div class="post-list">
      <div v-for="(post, index) in posts" :key="index" class="post">
        <h2>{{ post.title }}</h2>
        <p>{{ post.description }}</p>
        <div v-html="post.content"></div>
      </div>
    </div>
  </template>
  

  
  <style scoped>
  .post-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  
  .post {
    border: 1px solid #ccc;
    padding: 15px;
    border-radius: 8px;
  }
  
  h2 {
    font-size: 1.5rem;
    margin-bottom: 10px;
  }
  
  p {
    font-size: 1rem;
    margin-bottom: 10px;
  }
  
  div {
    font-size: 0.9rem;
    color: #333;
  }
  </style>
  