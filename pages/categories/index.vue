<script lang="ts" setup>
useHead({
  title: "Categories",
  meta: [
    {
      name: "description",
      content: "Categories",
    },
  ],
});

const { data: categories } = await useWpApi().getCatgories();
</script>
<template>
  <PageHeader title="Categories" class="font-serif text-red-800"> </PageHeader>
  <section class="py-10 px-20">
    <div>
      <div class="flex flex-wrap gap-5">
        <NuxtLink
          v-for="category in categories"
          :key="(category as any).id"
          :to="`/categories/${(category as any).slug}`"
          class="flex items-center justify-center py-1 px-4 rounded text-white bg-slate-700 shadow-md hover:scale-110 duration-200 text-xl uppercase"
        >
          <span class="font-semibold"># {{ (category as any).name }}</span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>
