<script setup lang="ts">
// import colorGenerator from "~~/utils/colorGenerator";
// import { useRoute, useHead } from "vue-router";
// import { useWpApi } from "~~/composables/wpApi";
// import PageHeader from "~~/components/PageHeader.vue";

useHead({
  title: "Categories",
  meta: [
    {
      name: "description",
      content: "Categories",
    },
  ],
});

const { data: categories } = await useWpApi().getCategories();
</script>

<template>
  <PageHeader title="Categories"></PageHeader>
  <section class="py-10">
    <div class="container">
      <div class="flex flex-wrap gap-5">
        <NuxtLink
          v-for="category in categories"
          :key="category.id"
          :to="`/categories/${category.slug}`"
          class="flex items-center justify-center py-2 px-4 rounded text-white shadow-md hover:shadow-lg duration-200 text-2xl uppercase"
          :style="{ backgroundColor: colorGenerator() }"
        >
          <span class="font-semibold">#{{ category.name }}</span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>
