<script setup lang="ts">
import MainLayout from '~/layouts/MainLayout.vue';

console.log('index page')

definePageMeta({
  layout: "main-layout",
});
</script>

<template>
  <MainLayout>
    <span class="text-blue-400">index page</span>
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
  </MainLayout>
</template>
