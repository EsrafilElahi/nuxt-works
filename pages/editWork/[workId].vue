<script setup lang="ts">
import ActionLayout from "~/layouts/ActionLayout.vue";

const title = ref("");
const subTitle = ref("");
const router = useRouter();
const route = useRoute();
const workId = route.params?.workId;

onMounted(() => {
  const allWorks = JSON.parse(localStorage.getItem("allWorks") || "[]") || [];
  const work = allWorks?.find((work: any) => work.id === workId);

  title.value = work.title;
  subTitle.value = work.subTitle;
});

const handleSubmit = () => {
  const allWorks = JSON.parse(localStorage.getItem("allWorks") || "[]") || [];
  const work = allWorks?.find((work: any) => work.id === workId);
  const restWork = allWorks?.filter((work: any) => work.id !== workId);

  const objWork: any = {
    id: work?.id,
    title: title?.value,
    subTitle: subTitle?.value,
    completed: work?.completed,
  };

  const newAllWorks = [...restWork, objWork];

  localStorage.setItem("allWorks", JSON.stringify(newAllWorks, null, 2));
  router.back();
};
</script>

<template>
  <ActionLayout title="Add Work">
    <div class="flex flex-col gap-10 w-full h-full !relative">
      <div class="w-full flex flex-col gap-1">
        <label for="title" class="!pl-1">title</label>
        <input
          name="title"
          v-model="title"
          class="w-full p-2 outline-none bg-amber-100 rounded-lg"
          placeholder="title"
        />
      </div>

      <div class="w-full flex flex-col gap-1">
        <label for="subTitle" class="!pl-1">subTitle</label>
        <input
          name="subTitle"
          v-model="subTitle"
          class="w-full p-2 outline-none bg-amber-100 rounded-lg"
          placeholder="subTitle"
        />
      </div>

      <button
        @click="handleSubmit"
        class="fixed bottom-10 !bg-cyan-300 !py-3 !px-10 rounded-xl translate-[-50%] left-[50%]"
      >
        submit
      </button>
    </div>
  </ActionLayout>
</template>
