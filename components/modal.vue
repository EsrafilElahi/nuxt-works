<script setup lang="ts">
const props = defineProps(["open", "className"]);
const emit = defineEmits(["onClose"]);
</script>

<template>
  <div
    v-show="open"
    class="min-w-full min-h-full !p-10 bg-[#0000003d] absolute left-0 top-0 xxxxxxxxxxxxxxxxxxx"
    @click.self="emit('onClose')"
  >
    <div
      class="flex justify-center items-center bg-white !min-w-[300px] min-h-[150px] rounded-lg relative !p-2"
      :class="className"
    >
      <slot />

      <span
        class="absolute left-2 top-2 cursor-pointer bg-amber-400 !p-1 !px-2 rounded"
        @click="emit('onClose')"
        >X</span
      >
    </div>
  </div>
</template>
