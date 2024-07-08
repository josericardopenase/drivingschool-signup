<template>
  <StepContainer title="Necesitamos que nos eches un garabato">
    <div class="flex justify-center mb-3 w-full">
      <PdfViewer @pdfViewed="onPdfViewed"></PdfViewer>
    </div>
    <SignInput :isInputEnabled="isInputEnabled"></SignInput>
  </StepContainer>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import StepContainer from "./StepContainer.vue";
import SignInput from "./SignInput.vue";
import PdfViewer from "./PdfViewer.vue";

const isInputEnabled = ref(false);

const onPdfViewed = () => {
  isInputEnabled.value = true;
};
</script>

<style scoped>
</style>
