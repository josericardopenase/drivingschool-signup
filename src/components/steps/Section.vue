<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
</script>

<template>
  <StepContainer title="¿En que sección quieres matricularte?">
    <div class="flex gap-5">
      <DrivingSchoolCard title="Paseo de chil"></DrivingSchoolCard>
      <DrivingSchoolCard title="Rafael Cabrera"></DrivingSchoolCard>
      <DrivingSchoolCard title="Miller bajo"></DrivingSchoolCard>
    </div>
  </StepContainer>
</template>

<style scoped>

</style>