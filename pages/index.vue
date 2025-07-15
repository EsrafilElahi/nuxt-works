<script setup lang="ts">
definePageMeta({
  layout: "main-layout",
});

const allWorks = computed(() => JSON.parse(localStorage.getItem("allWorks")) || []);
</script>

<template>
  <div class="relative">
    <div class="flex flex-col gap-5">
      <WorkItem v-for="work in allWorks" :work="work" :key="work.id" />
    </div>

    <AddWorkPlusIcon />
  </div>
</template>
