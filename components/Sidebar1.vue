<script lang="ts" setup>
const config = useRuntimeConfig();
const { data: list, pending } = await useFetch(
  `${config.public.apiUrlAfl}/api/api.php/records/menuweb`,
  {
    headers: {
      "x-api-key": config.public.apiKeyAfl,
    },
  }
);
</script>

<template>
  <div class="sm:w-1/3 md:1/4 w-full flex-shrink flex-grow-0 p-4">
    <div class="sticky top-0 p-4 bg-gray-100 rounded-xl w-full">
      <ul
        class="flex sm:flex-col overflow-hidden content-center justify-between"
      >
        <li
          v-for="(item, index) in list.records"
          :key="index"
          class="py-2 hover:bg-indigo-300 rounded"
        >
          <NuxtLink class="truncate" :to="`/${item.seo}`">
            <img
              src="//cdn.jsdelivr.net/npm/heroicons@1.0.1/outline/home.svg"
              class="w-7 sm:mx-2 mx-4 inline"
            />
            <span class="hidden sm:inline">{{ item.caption }}</span>
          </NuxtLink>
        </li>
      </ul>
    </div>
    <div class="bg-gray-50 rounded-xl border my-3 w-full">
      <div
        class="max-w-7xl mx-auto py-8 px-4 sm:px-6 lg:py-12 lg:px-8 lg:flex lg:items-center lg:justify-between"
      >
        <h2
          class="text-3xl font-extrabold tracking-tight text-gray-900 sm:text-4xl"
        >
          <span class="block text-indigo-600 overflow-ellipsis"
            >Made with Tailwind CSS!</span
          >
        </h2>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
