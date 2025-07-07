<script setup lang="ts">
import MainLayout from '~/layouts/MainLayout.vue';

console.log('index page')

definePageMeta({
  layout: "main-layout",
});
</script>

<template>
  <MainLayout title="Add Task">
    <span class="text-blue-400">index page</span>

  </MainLayout>
</template>
