<script lang="ts" setup>
defineProps<{
  title?: string;
}>();
</script>
<template>
  <section class="py-16 bg-gray-100">
    <div class="container">
      <h1 v-if="title" class="text-4xl font-bold">{{ title }}</h1>
      <slot />
    </div>
  </section>
</template>
