<template>
  <p class="text-2xl mb-4 text-center">{{ message }}</p>
</template>

<script setup lang="ts">
const props = defineProps({
  message: String,
});
</script>
