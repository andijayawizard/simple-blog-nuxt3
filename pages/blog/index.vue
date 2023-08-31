<script lang="ts" setup>
useHead({ title: "Blog" });
const config = useRuntimeConfig();
const { data: list, pending } = await useLazyAsyncData("blog", () =>
  $fetch(
    `${config.public.apiUrlAfl}/api/api.php/records/blog?filter=pub,eq,1`,
    {
      headers: {
        "x-api-key": config.public.apiKeyAfl,
      },
    }
  )
);
</script>

<template>
  <div v-if="pending">please wait, loading...</div>
  <div v-else class="flex flex-wrap">
    <div
      v-for="(item, index) in list.records"
      :key="index"
      class="max-w-sm rounded overflow-hidden shadow-lg mr-2"
    >
      <NuxtLink :to="`/blog/${item.id}`">
        <img
          class="w-full"
          :src="`${config.public.apiUrlAfl}/assets/uploads/images/blog/${item.acak}-1.jpg`"
          :alt="`${item.nama}`"
        />
      </NuxtLink>
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2" v-html="item.nama"></div>
        <p class="text-gray-700 text-base" v-html="item.rgks"></p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#photography</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#travel</span
        >
        <span
          class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#winter</span
        >
      </div>
    </div>
  </div>
</template>

<style scoped></style>
