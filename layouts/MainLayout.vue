<template>
  <div class="min-h-screen flex items-center flex-col min-w-[500px] max-w-[500px] w-full mx-auto relative">
    <header class="w-full !flex justify-between items-center bg-[#9395D3] !p-4">
      <h2 class="!text-[20px] !font-bold text-white" v-uppercase>works app</h2>

      <div class="flex gap-2 items-center">
        <span class="text-white">{{ new Date().toLocaleDateString() }}</span>
        <Icon name="line-md:calendar" size="25" style="color: white" />
      </div>
    </header>

    <main class="w-full h-full bg-[#c5c8f4] px-2 py-5">
      <slot />
    </main>
  </div>
</template>