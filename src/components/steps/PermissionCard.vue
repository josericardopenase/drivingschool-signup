<script setup lang="ts">

import {ref} from "vue";

const {title, icon, price, specs} = defineProps<{title : string, icon: string, price : number, specs: string[]}>()
const isClicked = ref(false)

</script>

<template>
  <div @click="isClicked = !isClicked " :class="'w-full bg-gray-100 p-6 rounded-2xl cursor-pointer ' + (isClicked ? ' border-2 border-green-500' : '')">
    <div class="font-semibold text-xl text-gray-700 flex items-center">
      <div class="h-[35px] w-[35px] rounded-full bg-green-500 flex justify-center items-center">
        <v-icon class="text-white" :name="icon" scale="1.2"></v-icon>
      </div>
      <div class="ml-3">
      Permiso {{title}}
      </div>
    </div>
    <ul class="list-disc ml-10 mt-4 text-gray-500">
      <li v-for="spec in specs">{{spec}}</li>
      <!-- ... -->
    </ul>
    <div class="mt-5 flex justify-between">
      <div class="text-gray-500">
      Precio base
      </div>
      <div class="font-semibold text-green-500">
        {{price}}€
      </div>
    </div>


  </div>
</template>

<style scoped>

</style>