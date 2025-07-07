<script setup lang="ts">
import ActionLayout from '~/layouts/ActionLayout.vue';


const works = ref([
  {
    id: 1,
    title: 'add work title 1',
    subTitle: 'subTitle 1',
    completed: false,
  },
  {
    id: 2,
    title: 'title 2',
    subTitle: 'subTitle 2',
    completed: false,
  },
  {
    id: 3,
    title: 'title 3',
    subTitle: 'subTitle 3',
    completed: true,
  },
  {
    id: 4,
    title: 'title 4',
    subTitle: 'subTitle 4',
    completed: false,
  },
])

</script>

<template>
  <ActionLayout title="Add Work">
    <div>
      <div class="flex flex-col gap-5">
        <WorkItem v-for="work in works" :work="work" :key="work.id" />
      </div>
    </div>
  </ActionLayout>
</template>
