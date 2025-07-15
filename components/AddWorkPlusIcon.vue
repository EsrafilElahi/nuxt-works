<script setup lang="ts">

const router = useRouter();

const redirectToAddWorkPage = () => {
  router.push('/addWork');
}

</script>

<template>
  <div
    class="flex justify-center items-center bg-[#9395D3] rounded-full !p-4 shadow-2xl fixed right-10 bottom-10 cursor-pointer"
    @click="redirectToAddWorkPage">
    <Icon name="material-symbols:add" size="30" style="color: white; cursor: pointer;" @click="" />
  </div>
</template>
