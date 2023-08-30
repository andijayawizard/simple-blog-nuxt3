<script lang="ts" setup></script>

<template>
  <div class="w-full flex flex-col sm:flex-row flex-grow overflow-hidden">
    <Sidebar1 />
    <main role="main" class="w-full h-full flex-grow p-3 overflow-auto">
      <slot />
    </main>
  </div>
  <Footer1 />
</template>

<style scoped></style>
