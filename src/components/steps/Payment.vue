<script setup lang="ts">

import StepContainer from "./StepContainer.vue";
import DrivingSchoolCard from "./DrivingSchoolCard.vue";
import PermissionCard from "./PermissionCard.vue";
import Input from "./Input.vue";
</script>

<template>
  <StepContainer title="Rellena tus datos personales">
    <div class="flex gap-3">
      <div class="flex flex-col gap-3 w-full">
        <div class="mt-2 flex flex-col gap-3">
          <p class="font-semibold text-gray-500">Datos de facturación</p>
          <Input placeholder="Dirección de facturación" name="direction"></Input>
          <Input placeholder="Ciudad" name="first_surname"></Input>
          <Input placeholder="Provincia" name="second_surname"></Input>
          <Input placeholder="Codigo postal" name="email"></Input>
        </div>
      </div>
      <div class="w-full bg-gray-100 rounded-xl p-5">
        <p class="font-semibold text-gray-500">Tu pedido</p>
        <div class="flex items-center justify-between mt-5 ">
          <p class="font-semibold text-xl text-gray-700">MÁTRICULA B MANUAL</p>
          <p class="font-semibold text-green-500">40$</p>
        </div>
        <div class="flex flex-col gap-2 mt-10">
          <div class="flex items-center justify-between ">
            <p class="font-semibold text-md text-gray-700">Subotal</p>
            <p class="font-semibold text-green-500">40$</p>
          </div>
          <div class="flex items-center justify-between ">
            <p class="font-semibold text-md text-gray-700">Total (7% IGIC incluido)</p>
            <p class="font-semibold text-green-500">43.5$</p>
          </div>
        </div>
      </div>
    </div>
  </StepContainer>
</template>

<style scoped>

</style>