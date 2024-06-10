<template>
  <div>
    <img :src="src" class="w-full h-72 object-cover border" />
  </div>
</template>

<script setup>
const props = defineProps({
  src: {
    type: String,
    required: true,
  },
});
</script>
