<script lang="ts" setup>
defineProps<{
  title?: string;
}>();
</script>
<template>
  <section class="p-6 bg-black">
    <div class="">
      <h1 v-if="title" class="text-4xl font-bold">{{ title }}</h1>
      <slot />
    </div>
  </section>
</template>
