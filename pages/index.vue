<template>
  <!-- <div class="flex justify-end bg-slate-900 p-1">
    <div class="flex-1 rounded-md">
      <div
        class="flex hover:bg-slate-600 font-serif hover:scale-110 duration-300 w-fit ml-10 rounded-md p-1 text-xl"
      >
        <Avatar
          src="https://vntime.org/wp-content/uploads/2020/04/100-%E1%BA%A2nh-n%E1%BB%81n-m%C3%A1y-t%C3%ADnh-%C4%91%E1%BA%B9p-nh%E1%BA%A5t-c%C3%B3-link-t%E1%BA%A3i-v%E1%BB%81-tr%E1%BB%B1c-ti%E1%BA%BFp.jpeg"
        />
        <button class="flex justify-center items-center p-2 text-white">
          IT Blogggg
        </button>
      </div>
    </div>
    <button
      class="p-2 ml-4 rounded-md text-white hover:bg-slate-800 hover:scale-110 duration-300"
    >
      Home
    </button>

    <button
      class="p-2 mr-10 ml-4 rounded-md text-white hover:bg-slate-800 hover:scale-110 duration-300"
    >
      Categories
    </button>
  </div>
  <div class="bg-clip-text">
    <Image
      src="https://media.istockphoto.com/id/1289411982/vi/anh/an-ninh-m%E1%BA%A1ng-ph%C3%A1t-tri%E1%BB%83n-web-v%C3%A0-l%C3%A0m-vi%E1%BB%87c-trong-kh%C3%A1i-ni%E1%BB%87m-it.jpg?s=612x612&w=0&k=20&c=6NZTGJASgJN2vdY9sRVsxSg_UuNDo-qQpmen4hhafZ8="
    />
  </div> -->
  <main>
    <PageHeader>
      <div class="flex items-center flex-wrap">
        <div
          class="avatar relative h-[200px] w-[200px] rounded overflow-hidden mr-10 mb-5 sm:mb-0 shadow-xl"
        >
          <img src="" class="absolute w-full h-full object-cover" />
        </div>
        <div>
          <h1 class="text-4xl font-bold">IT Blogggg</h1>
          <p class="mt-3 text-xl mb-5"></p>
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

<script setup>
import useWpApi from "~~/composables/useWpApi";

useHead({
  title: "Home",
  meta: [
    {
      name: "description",
      content: "Home",
    },
  ],
  titleTemplate: "IT Blogggg",
});
const { data: blogs, refresh, error } = await useWpApi().getPosts();
</script>
