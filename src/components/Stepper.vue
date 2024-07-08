<script setup lang="ts">

import Step from "./Step.vue";
import Welcome from "./steps/Welcome.vue";
import Section from "./steps/Section.vue";
import {ref} from "vue";
import Permission from "./steps/Permission.vue";
import PersonalData from "./steps/PersonalData.vue";
import Facturation from "./steps/Facturation.vue";
import Payment from "./steps/Payment.vue";
import Sign from "./steps/Sign.vue";
import Start from "./steps/Start.vue";
import PermissionOptions from "./steps/PermissionOptions.vue";

const steps = [
   {
     title : "Bienvenido",
     component: Welcome
  },
  {
    title: "Sucursal",
    component: Section
  },
  {
    title: "Permiso",
    component: Permission
  },
  {
    title: "Permiso options",
    component: PermissionOptions,
    hidden: true,
    related: 2
  },
  {
    title: "Datos personales",
    component: PersonalData
  },
  {
    title: "Pago",
    component: Payment
  },
  {
    title: "Firma del contrato",
    component: Sign
  },
  {
    title: "Comienza a estudiar",
    component: Start
  }
]

const active = ref(0)

</script>

<template>
  <div class="w-full h-[100vh]">
    <div id="sidebar" class="w-[330px] bg-green-500 h-[100vh] p-5 fixed">
      <div class="text-3xl text-white font-semibold">
        Autoescuela ECO
      </div>
      <div class="flex flex-col gap-3 mt-10 relative">
        <div class="absolute h-[500px] ml-[35px] mt-[20px] w-[2px] bg-white"></div>
        <Step v-for="(step, index) in steps" :key="active" :title="step.title" :index="index + 1" :class="step.hidden ? 'hidden' : ''" :is-active="active == index || index == steps[active].related"></Step>
      </div>
    </div>
    <div class="pl-[340px] w-full flex justify-center items-center  z-20">
      <div class="w-full max-w-[900px] mt-40 mb-20">
        <component :is="steps[active].component"></component>
        <div class="w-full flex justify-center gap-3 mt-20">
          <div class="w-full flex justify-center gap-3 max-w-[500px]">
            <button
                @click="active = Math.max(active - 1, 0)"
                class="w-full py-3 bg-gray-100 text-gray-700 font-semibold rounded-full cursor-pointer hover:bg-gray-200 transition-all"
            >
              Anterior
            </button>
            <button
                @click="active = Math.min(active + 1, steps.length - 1)"
                class="w-full py-3 bg-green-500 text-white font-semibold rounded-full cursor-pointer hover:bg-green-600 transition-all"
            >
              Siguiente
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>