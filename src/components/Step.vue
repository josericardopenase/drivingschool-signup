<script setup lang="ts">
const {isActive, title, index} = defineProps<{isActive: boolean, title : string, index: number}>()

const indexClass = "w-[30px] h-[30px] border-2 font-semibold flex items-center justify-center rounded-full " + (isActive ? "border-gray-500 text-gray-600" : "border-white text-white bg-green-500")
const bodyClass = "w-full  cursor-pointer p-5 rounded-2xl z-10" + (isActive ? " bg-white shadow-sm" : " ")
const titleClass = "text-lg font-semibold " + (isActive ? "text-gray-600" : "text-white")
</script>

<template>
  <div :class="bodyClass ">

    <div class="flex items-center gap-4">
      <div :class="indexClass">
        {{index}}
      </div>
      <div :class="titleClass">
        {{title}}
      </div>
    </div>

  </div>
</template>

<style scoped>

</style>