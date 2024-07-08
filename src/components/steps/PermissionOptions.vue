<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
import PermissionCard from "./PermissionCard.vue";
import CheckboxInput from "./CheckboxInput.vue";

const checkboxOptions = [
  { label: 'No dispongo del carnet B1', value: 'option1', price: 5 },
];
</script>

<template>
  <StepContainer title="Elige las opciones que mas se adecuen">
    <CheckboxInput :options="checkboxOptions" name="options"></CheckboxInput>
  </StepContainer>
</template>

<style scoped>

</style>