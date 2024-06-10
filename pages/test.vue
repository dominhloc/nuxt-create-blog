<template>
  <main>
    <PageHeader>
      <div class="flex items-center flex-wrap">
        <div
          class="avatar relative h-[200px] w-[200px] rounded overflow-hidden mr-10 mb-5 sm:mb-0 shadow-xl"
        >
          <img
            src="~/assets/img/1187753.png"
            class="absolute w-full h-full object-cover"
          />
        </div>
        <div>
          <h1 class="text-4xl font-bold">Thành Kun</h1>
          <p class="mt-3 text-xl mb-5"></p>
          <a
            href="https://www.facebook.com/profile.php?id=100023987322376"
            class="bg-blue-600 hover:bg-blue-700 py-2 px-4 rounded text-white inline-flex items-center gap-2"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              viewBox="0 0 320 512"
            >
              <path
                fill="currentColor"
                d="m279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
              />
            </svg>
            Let's Connect
          </a>
        </div>
      </div>
    </PageHeader>

    <!-- Blog Section Starts -->
    <section class="blogs">
      <div class="container py-10">
        <div class="grid sm:grid-cols-3 gap-10">
          <BlogGrid
            v-for="blog in blogs"
            :key="blog.id"
            :title="blog.title.rendered"
            :image="blog._embedded['wp:featuredmedia'][0]?.source_url"
            :excerpt="blog.excerpt.rendered"
            :slug="blog.slug"
          ></BlogGrid>
        </div>
      </div>
    </section>
    <!-- Blog Section Ends  -->
  </main>
</template>
<script lang="ts" setup>
import useWpApi from "~~/composables/useWpApi";

useHead({
  title: "Home",
  meta: [
    {
      name: "description",
      content: "Home",
    },
  ],
  titleTemplate: "Thành Kun",
});
const { data: blogs, refresh, error } = await useWpApi().getPosts();
</script>
