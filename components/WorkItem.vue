<script setup lang="ts">
const openDelete = ref(false);
const openComplete = ref(false);
const router = useRouter();

const props = defineProps(["work"]);
const allWorks = JSON.parse(localStorage.getItem("allWorks") || "[]") || [];

const handleDelete = () => {
  const restAllWorks = allWorks?.filter(
    (item: any) => item.id !== props.work.id
  );

  localStorage.setItem("allWorks", JSON.stringify(restAllWorks, null, 2));

  openDelete.value = false;
};

const handleComplete = () => {
  const foundWork = allWorks?.find((item: any) => item.id === props.work.id);
  const restAllWorks = allWorks?.filter(
    (item: any) => item.id !== props.work.id
  );

  foundWork.completed = !foundWork.completed;

  localStorage.setItem(
    "allWorks",
    JSON.stringify([...restAllWorks, foundWork], null, 2)
  );

  openComplete.value = false;
};

const handlePushToEditWork = () => {
  router.push(`/editWork/${props.work.id}`)
}

</script>

<template>
  <div
    class="flex justify-between items-center gap-10 !px-4 !border !border-gray-300 !py-2 rounded-lg shadow-xl bg-white"
  >
    <div>
      <h5 class="!text-[23px] !font-bold text-[#9395D3]" v-uppercase>
        {{ work?.title }}
      </h5>
      <span class="!text-[15px] mt-1">{{ work?.subTitle }}</span>
    </div>

    <div class="flex justify-between items-center gap-5">
      <Icon
        name="material-symbols:edit-outline"
        size="20"
        class="hover:bg-yellow-400"
        style="color: #b3b7ee; cursor: pointer"
        @click="handlePushToEditWork"
      />
      <Icon
        name="material-symbols-light:delete-sharp"
        class="hover:bg-red-400"
        size="23"
        :style="{ color: '#B3B7EE', cursor: 'pointer' }"
        @click="openDelete = true"
      />
      <Icon
        name="nrk:media-media-complete"
        size="20"
        class="hover:bg-green-400"
        :style="{
          color: work?.completed ? 'green' : '#B3B7EE',
          cursor: 'pointer',
        }"
        @click="openComplete = true"
      />
    </div>

    <Modal :open="openDelete" @onClose="openDelete = false">
      <div class="w-full flex justify-between items-center">
        <button
          class="!bg-green-300 !py-3 !px-10 rounded-xl"
          @click="handleDelete"
        >
          yes
        </button>
        <button
          class="!bg-red-300 !py-3 !px-10 rounded-xl"
          @click="openDelete = false"
        >
          no
        </button>
      </div>
    </Modal>

    <Modal :open="openComplete" @onClose="openComplete = false">
      <div class="w-full flex justify-between items-center">
        <button
          class="!bg-green-300 !py-3 !px-10 rounded-xl"
          @click="handleComplete"
        >
          yes
        </button>
        <button
          class="!bg-red-300 !py-3 !px-10 rounded-xl"
          @click="openComplete = false"
        >
          no
        </button>
      </div>
    </Modal>
  </div>
</template>
