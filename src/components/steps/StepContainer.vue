<script setup lang="ts">
const { title } = defineProps<{ title: string }>();

function formatTitle(title: string): string {
  // Replace **text** with <span class="text-green-500">text</span>
  let formattedTitle = title.replace(/\*\*(.*?)\*\*/g, '<span class="text-green-500">$1</span>');

  // Replace _text_ with <em>text</em>
  formattedTitle = formattedTitle.replace(/_(.*?)_/g, '<em>$1</em>');

  // Replace \n with <br>
  formattedTitle = formattedTitle.replace(/\\intro/g, '<br>');

  return formattedTitle;
}
</script>

<template>
  <div class="mt-10">
    <div class="w-full text-center text-3xl font-semibold" v-html="formatTitle(title)">
    </div>
    <div class="mt-20">
    <slot/>
    </div>
  </div>
</template>

<style scoped>
</style>
