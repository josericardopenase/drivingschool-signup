<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
</script>

<template>
  <StepContainer title="Es momento de empezar a estudiar">
    <p class="text-gray-500 text-center font-semibold text-lg">Tranquilo... Se que tienes muchas dudas ahora mismo de como comenzar con tu estudio, no te preocupes. Aqui te dejamos un video para que te aclares</p>
  </StepContainer>
  <div class="w-full flex justify-center bg-gray-100 rounded-lg mt-5 ">
    <video width="640" height="360" controls>
    </video>
  </div>
</template>

<style scoped>

</style>