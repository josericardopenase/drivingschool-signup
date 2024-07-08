<template>
  <div class="w-full max-w-[500px]">
    <a href="https://www.orimi.com/pdf-test.pdf" target="_blank" @click="onPdfViewed" class="  transition-all w-full flex gap-3 items-center bg-gray-100 p-4 rounded-xl cursor-pointer hover:bg-gray-200">
      <div class="h-[50px] w-[50px] rounded-full bg-gray-200 flex justify-center items-center">
        <v-icon class="text-gray-500" scale="1.2" name="fa-eye"></v-icon>
      </div>
      <div class="text-gray-500 font-semibold text-lg">
        Ver el contrato
      </div>
    </a>
  </div>
</template>

<script setup lang="ts">
import { defineEmits } from 'vue';

const emit = defineEmits(['pdfViewed']);

const onPdfViewed = () => {
  emit('pdfViewed');
};
</script>

<style scoped>
</style>
