<template>
  <div class="text-xl font-semibold text-gray-500">
    <label v-for="(option, index) in options" :key="index" class="flex items-center space-x-2">
      <input id="vue-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
      <span>{{ option.label }}</span>
      <spanl class="text-green-500">+{{ option.price }}€</spanl>
    </label>
  </div>
</template>

<script setup lang="ts">
import { defineProps, ref } from 'vue';

const {options} = defineProps<{ options: Array<{ label: string, value: string, price: number }>, name: string }>();

const selectedOptions = ref<string[]>([]);
</script>

<style scoped>
input {
  width: auto;
  height: auto;
  margin-right: 0.5rem;
}

label {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}
</style>
