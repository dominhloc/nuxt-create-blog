<template>
  <nav
    class="bg-gray-900 text-white py-5 border-b border-gray-700 flex justify-end p-1"
  >
    <div class="flex-1 rounded-md">
      <div
        class="flex hover:bg-slate-600 font-serif hover:scale-110 duration-300 w-fit ml-10 rounded-md p-1 text-xl"
      >
        <Avatar
          src="https://vntime.org/wp-content/uploads/2020/04/100-%E1%BA%A2nh-n%E1%BB%81n-m%C3%A1y-t%C3%ADnh-%C4%91%E1%BA%B9p-nh%E1%BA%A5t-c%C3%B3-link-t%E1%BA%A3i-v%E1%BB%81-tr%E1%BB%B1c-ti%E1%BA%BFp.jpeg"
        />
        <NuxtLink
          to="/"
          class="text-2xl font-medium ml-4 p-2 rounded-md flex justify-center items-center text-white"
          >IT Blogggg</NuxtLink
        >
      </div>
      <ul
        class="flex gap-5 items-center justify-end text-gray-300 hover:text-gray-50"
      >
        <li :class="active === '/' ? 'text-primary-400' : ''">
          <NuxtLink to="/">Home</NuxtLink>
        </li>
        <li :class="active === '/categories' ? 'text-primary-400' : ''">
          <NuxtLink to="/categories">Categories</NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script lang="ts" setup>
const route = useRoute();
const active = computed(() => {
  return route.path;
});
</script>
