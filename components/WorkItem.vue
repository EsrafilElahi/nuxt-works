<script setup lang="ts">

const props = defineProps(['work']);

</script>

<template>
  <div
    class="flex justify-between items-center gap-10 !px-4 !border !border-gray-300 !py-2 rounded-lg shadow-xl bg-white">
    <div>
      <h5 class="!text-[23px] !font-bold text-[#9395D3]" v-uppercase>{{ work?.title }}</h5>
      <span class="!text-[15px] mt-1">{{ work?.subTitle }}</span>
    </div>

    <div class="flex justify-between items-center gap-5">
      <Icon name="material-symbols:edit-outline" size="20" style="color: #B3B7EE; cursor: pointer;" @click="" />
      <Icon name="material-symbols-light:delete-sharp" size="23" style="color: #B3B7EE; cursor: pointer;" @click="" />
      <Icon name="nrk:media-media-complete" size="20"
        :style="{ color: work?.completed ? 'green' : '#B3B7EE', cursor: 'pointer' }" @click="" />
    </div>

  </div>
</template>
