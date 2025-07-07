<script setup lang="ts">
import type { RouteLocationAsPath, RouteLocationAsPathGeneric } from 'vue-router';

const props = defineProps(['title']);
const router = useRouter();
const route: RouteLocationAsPathGeneric = useRoute();

console.log(route)

const handleBack = () => {
  router.back()
}
</script>

<template>
  <div class="min-h-screen flex items-center flex-col min-w-[500px] max-w-[500px] w-full mx-auto">
    <header class="w-full !flex justify-start gap-7 items-center bg-[#9395D3] !p-4">
      <Icon name="material-symbols:arrow-back-rounded" size="30" style="color: white; cursor: pointer;"
        @click="handleBack" />
      <h2 class="!text-[20px] !font-bold text-white">{{ title
        }}</h2>
    </header>

    <main class="w-full h-full bg-[#c5c8f4] px-2 py-5">
      <slot />
    </main>
  </div>
</template>