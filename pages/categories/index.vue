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
  <div class="flex justify-center items-center bg-black">
    <PageHeader
      title="Categories"
      class="font-serif text-white flex-1 justify-center items-center flex"
    >
    </PageHeader>
  </div>
  <section class="py-10 px-20 flex justify-center">
    <div>
      <div class="flex flex-col space-y-3 items-center w-96">
        <NuxtLink
          v-for="category in categories"
          :key="(category as any).id"
          :to="`/categories/${(category as any).slug}`"
          class="py-1 px-4 rounded-lg text-white bg-slate-500 hover:bg-slate-800 shadow-md hover:scale-125 duration-75 text-xl uppercase"
        >
          <span class="font-semibold"># {{ (category as any).name }}</span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>
