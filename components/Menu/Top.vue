<template>
  <div class="flex justify-center max-w-full bg-slate-200">
    <div class="text-black p-4 flex-1 max-w-7xl">
      <div class="flex space-x-5">
        <!-- Nút Blog về Trang chủ -->
        <div class="flex-auto flex items-center">
          <NuxtLink
            to="/"
            class="flex justify-start border-black items-center text-3xl font-serif font-semibold hover:scale-125 duration-300 border p-1 rounded-md"
          >
            Blog
          </NuxtLink>
        </div>
        <div class="flex space-x-5 items-center mr-4">
          <!-- Trang chủ -->
          <div
            :class="
              isActive('/')
                ? 'bg-slate-400 rounded-md hover:scale-150 duration-300'
                : 'hover:scale-150 duration-300'
            "
          >
            <button
              @click.prevent="navigate('/')"
              class="font-serif font-semibold p-2 border border-black rounded-md"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1.2em"
                height="1.2em"
                viewBox="0 0 24 24"
                class="text-xl"
              >
                <path
                  fill="black"
                  d="M6 19h3v-6h6v6h3v-9l-6-4.5L6 10zm-2 2V9l8-6l8 6v12h-7v-6h-2v6zm8-8.75"
                />
              </svg>
            </button>
          </div>
          <div
            :class="
              isActive('/categories')
                ? 'bg-slate-400 rounded-md hover:scale-150 duration-300'
                : 'hover:scale-150 duration-300'
            "
          >
            <button
              @click.prevent="navigate('/categories')"
              class="font-serif font-semibold p-2 border-black border rounded-md"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1.2em"
                height="1.2em"
                viewBox="0 0 32 32"
                class="text-xl"
              >
                <path
                  fill="black"
                  d="m6.76 6l.45.89L7.76 8H12v5H4V6zm.62-2H3a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1V7a1 1 0 0 0-1-1H9l-.72-1.45a1 1 0 0 0-.9-.55m15.38 2l.45.89l.55 1.11H28v5h-8V6zm.62-2H19a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1V7a1 1 0 0 0-1-1h-4l-.72-1.45a1 1 0 0 0-.9-.55M6.76 19l.45.89l.55 1.11H12v5H4v-7zm.62-2H3a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1v-7a1 1 0 0 0-1-1H9l-.72-1.45a1 1 0 0 0-.9-.55m15.38 2l.45.89l.55 1.11H28v5h-8v-7zm.62-2H19a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1v-7a1 1 0 0 0-1-1h-4l-.72-1.45a1 1 0 0 0-.9-.55"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// import { useRoute, useRouter } from "vue-router";
// import { computed } from "vue";

const route = useRoute();
const router = useRouter();

const isActive = (path) => {
  return route.path === path;
};

const navigate = (path) => {
  router.push(path);
};
</script>
