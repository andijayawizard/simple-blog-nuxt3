<script lang="ts" setup></script>

<template>
  <div class="container mx-auto">
    <div class="flex flex-row flex-wrap py-4">
      <Sidebar />
      <main role="main" class="w-full sm:w-2/3 md:w-3/4 pt-1 px-2">
        <slot />
      </main>
    </div>
  </div>
  <Footer />
</template>

<style scoped></style>
