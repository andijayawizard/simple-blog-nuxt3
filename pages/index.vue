<script lang="ts" setup>
const data = {
  title: "Welcome to nuxt 3",
  desc: "percobaan pertama pake nuxt, good luck",
};
useHead({ title: data.title });
definePageMeta({ layout: false });
const layout = ref("custom1");
</script>

<template>
  <NuxtLayout :name="layout">
    <div>
      <h1 class="text-3xl md:text-5xl mb-4 font-extrabold" id="home">
        Single-page App Layout
      </h1>
      <p class="py-2 text-xl">
        This single-page "app" style layout features a
        <span class="font-bold">sidebar</span>,
        <span class="font-bold">main</span> content area, and
        <span class="font-bold">footer</span>. This full-height layout is never
        more than viewport height. The content area scrolls independently as
        needed. For this example, we're using the
        <a class="text-indigo-600" href="https://tailwindcss.com/"
          >Tailwind CSS</a
        >
        utility framework. As part of it's default classes, Tailwind includes
        Flexbox classes which make this layout implementation simple!
      </p>
      <p class="py-2 text-xl">
        Additionally, this layout is <span class="italic">responsive</span>. As
        screen width decreases down to 640px (the smallest Tailwind breakpoint),
        the layout stacks vertically. The sidebar orientation is flipped from
        vertical to horizontal (<code>flex-col sm:flex-row</code>), and the main
        content area fills the remaining height above the footer.
      </p>
    </div>
  </NuxtLayout>
</template>

<style scoped></style>
