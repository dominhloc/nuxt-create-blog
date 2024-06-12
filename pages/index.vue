<template>
  <main>
    <PageHeader>
      <div class="flex flex-col items-center justify-center">
        <div class="h-[300px] w-screen">
          <img
            src="https://cdn.tgdd.vn/Files/2020/09/20/1291843/chip-concept_800x450.jpg"
            class="w-full h-full object-cover"
          />
        </div>
      </div>
    </PageHeader>

    <!-- Blog Section Starts -->
    <section class="blogs">
      <div class="py-10">
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
  titleTemplate: "Blog",
});
const { data: blogs, refresh, error } = await useWpApi().getPosts();
</script>
