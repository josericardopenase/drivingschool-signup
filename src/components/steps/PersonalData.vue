<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
import PermissionCard from "./PermissionCard.vue";
import Input from "./Input.vue";
</script>

<template>
  <StepContainer title="Rellena tus datos personales">
    <div class="flex flex-col gap-3">
      <p class="font-semibold text-gray-500">Datos alumno</p>
    <Input placeholder="Nombre del alumno" name="name"></Input>
      <Input placeholder="Email" name="email"></Input>
      <div class="w-full flex gap-3">
        <Input placeholder="DNI" name="dni"></Input>
        <Input placeholder="Teléfono" name="phone"></Input>
        <Input placeholder="Fecha de nacimiento" name="birthdate" type="date"></Input>
      </div>
      <p class="font-semibold text-gray-500">Dirección del alumno</p>
      <Input placeholder="Dirección" name="direction"></Input>
      <div class="flex justify-between gap-4">
        <Input placeholder="Ciudad" name="first_surname"></Input>
        <Input placeholder="Provincia" name="second_surname"></Input>
        <Input placeholder="Codigo postal" name="email"></Input>
      </div>
    </div>
  </StepContainer>
</template>

<style scoped>

</style>