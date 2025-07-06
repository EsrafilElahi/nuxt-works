<template>
  <div class="min-h-screen flex items-center flex-col min-w-[500px] max-w-[500px] w-full mx-auto">
    <header class="w-full !flex justify-between items-center bg-[#9395D3] !p-4">
      <h2 class="text-2xl font-bold text-white" style="font-weight: 700;" v-uppercase>works app</h2>

      <div class="flex gap-2 items-center">
        <span class="text-white">{{ new Date().toLocaleDateString() }}</span>
        <Icon name="line-md:calendar" size="16" style="color: white" />
      </div>
    </header>

    <main class="w-full h-full bg-[#B3B7EE] px-2 py-5">
      <slot />
    </main>
  </div>
</template>