<script setup>
const params = useRoute().params;

const { data: posts } = await useWpApi().getPost(params.slug);
const post = posts.value?.[0];

useHead({
  title: post?.title.rendered,
  meta: [
    {
      name: "description",
      content: `${post?.excerpt.rendered}`,
    },
  ],
});
</script>

<template>
  <section class="container blog py-10 sm:py-16">
    <div v-if="post" class="sm:px-20">
      <!-- Tiêu đề blog -->
      <h1 class="text-3xl sm:text-5xl font-bold text-center leading-snug mb-5">
        {{ post.title.rendered }}
      </h1>
      <!-- Meta blog -->
      <div class="flex mb-10 justify-center gap-5">
        <span>
          Viết bởi:
          <span class="text-primary-500">{{
            post._embedded["author"][0]?.name
          }}</span>
        </span>

        <span>
          Đăng vào:
          <span class="text-primary-500">{{ post.date }}</span>
        </span>
      </div>
      <!-- Hình ảnh blog -->
      <div
        class="h-[250px] sm:h-[500px] w-full rounded shadow-xl relative overflow-hidden mb-12"
      >
        <img
          :src="post._embedded['wp:featuredmedia'][0]?.source_url"
          :alt="post.title.rendered"
          class="absolute w-full h-full object-cover"
        />
      </div>
      <div class="sm:px-10">
        <div v-if="post.content" v-html="post.content.rendered"></div>
      </div>
    </div>
  </section>
</template>
