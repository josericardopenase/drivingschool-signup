<script setup lang="ts">

import ds from "../../assets/ds.jpeg";
import {ref} from "vue";

const {title} = defineProps<{title : string}>()
const isClicked = ref(false)

</script>

<template>
  <div @click="isClicked = !isClicked" :class="'w-[300px] bg-gray-100 p-3 pb-5 text-center rounded-2xl cursor-pointer ' + (isClicked ? ' border-2 border-green-500' : '') ">
    <img :src="ds" class="rounded-2xl">
    <div class="font-semibold text-xl mt-4">
      {{title}}
    </div>
    <a target="_blank" href="https://www.google.com/maps?ll=28.105301,-15.414084&z=16&t=m&hl=es&gl=ES&mapclient=embed&cid=11684013949295649842">
      <button class="bg-green-500 py-1 px-4 rounded-full font-semibold text-white mt-3 cursor-pointer">
        Ver mapa
      </button>
    </a>
  </div>
</template>

<style scoped>

</style>