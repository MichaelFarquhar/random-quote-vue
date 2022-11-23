<script setup>
defineProps({
  content: String,
  author: String,
  isLoading: Boolean,
});
</script>

<template>
  <button v-if="isLoading" class="btn btn-ghost loading"></button>
  <h2 v-if="!isLoading" className="card-title justify-center">{{ content }}</h2>
  <p v-if="!isLoading" className="italic">- {{ author }}</p>
</template>
