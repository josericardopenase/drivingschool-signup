<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
import PermissionCard from "./PermissionCard.vue";
</script>

<template>
  <StepContainer title="¿En que permiso te vas a dar de alta?">
    <div class="flex gap-5">
      <PermissionCard price="40" title="B2" icon="fa-car" :specs="['Conducción de turismo','Carnet A1 con dos años de antiguedad', 'edad mínima 18 años']"></PermissionCard>
      <PermissionCard price="40" title="AM" icon="fa-motorcycle" :specs="['Hasta 50cc', 'No mas de 13 CV', 'edad mínima 16 años']"></PermissionCard>
    </div>
    <div class="flex gap-5 mt-5">
      <PermissionCard price="40" title="A2" icon="fa-motorcycle" :specs="['Conducción de turismo','Carnet A1 con dos años de antiguedad', 'edad mínima 18 años']"></PermissionCard>
      <PermissionCard price="40" title="A" icon="fa-motorcycle" :specs="['Motos de cualquier cilindrada y cualquier CV', '2 años de antiguedad de A2']"></PermissionCard>
    </div>
  </StepContainer>
</template>

<style scoped>

</style>