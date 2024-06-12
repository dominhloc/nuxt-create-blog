<script setup>
const props = defineProps({
  title: String,
  image: String,
  slug: String,
});
</script>

<template>
  <div class="grid shadow-xl group overflow-hidden rounded">
    <div
      v-if="image"
      class="grid__image group h-[300px] w-full relative overflow-hidden"
    >
      <img
        :src="image"
        :alt="title"
        class="absolute w-full h-full group-hover:scale-110 duration-300 object-fill"
      />
    </div>
    <div class="p-5 space-y-4">
      <h3 class="text-xl group-hover:text-blue-600 font-semibold">
        {{ title }}
      </h3>

      <NuxtLink
        v-if="slug"
        class="border-b-2 border-blue-500 group-hover:font-semibold inline-flex items-center"
        :to="`/${slug}`"
      >
        Read more
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-4 h-4 ml-1 group-hover:ml-4 group-hover:font-semibold duration-200"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4.5 12h15m0 0l-6.75-6.75M19.5 12l-6.75 6.75"
          />
        </svg>
      </NuxtLink>
    </div>
  </div>
</template>
