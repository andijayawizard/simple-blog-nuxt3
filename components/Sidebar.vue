<script lang="ts" setup>
const config = useRuntimeConfig();
const { data: list, pending } = await useAsyncData("menuweb", () =>
  $fetch(`${config.public.apiUrlAfl}/api/api.php/records/menuweb`, {
    headers: {
      "x-api-key": config.public.apiKeyAfl,
    },
  })
);
</script>

<template>
  <aside class="w-full sm:w-1/3 md:w-1/4 px-2">
    <div class="sticky top-0 p-4 bg-white rounded-xl w-full">
      <ul class="nav flex flex-col overflow-hidden">
        <li v-for="(item, index) in list.records" :key="index" class="nav-item">
          <NuxtLink
            :to="`/${item.seo}`"
            class="nav-link text-purple-800 hover:text-purple-600 truncate"
          >
            <span class="fa fa-home mr-2"></span> {{ item.caption }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </aside>
</template>

<style scoped></style>
