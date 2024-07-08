<script setup lang="ts">
const { placeholder, name } = defineProps<{placeholder : string, name : string }>()

</script>

<template>
  <input :placeholder="placeholder" :name="name" class="bg-gray-100 w-full p-3 rounded-xl px-5">
  </input>
</template>

<style scoped>

</style>