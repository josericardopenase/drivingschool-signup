<template>
  <div id="app" class="flex flex-col gap-0 relative">
    <p class="font-semibold text-gray-500 mb-3 text-lg">Firma aquí</p>
    <canvas id="canvas" class="rounded-xl" height="300px" :class="isInputEnabled ? 'block': 'hidden'"></canvas>
    <div v-if="!isInputEnabled" class="w-full h-[250px] bg-gray-50 rounded-xl flex justify-center items-center flex-col">
      <v-icon name="fa-lock" scale="3" class="text-gray-500"></v-icon>
      <p class="text-xl mt-5 text-gray-500">
      Tienes que visualiar el contrato primero
      </p>
    </div>
    <input type="text" v-model="exampleContent" :disabled="!isInputEnabled" />
    <button class="p-2 px-7 rounded-xl text-white hover:bg-green-600 bg-green-500 font-semibold w-fit" @click="clearCanvas" :disabled="!isInputEnabled">Limpiar</button>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount, defineProps } from 'vue';

const props = defineProps({
  isInputEnabled: {
    type: Boolean,
    required: true
  }
});

const exampleContent = ref('');
let isDrawing = false;
let canvas: HTMLCanvasElement;
let ctx: CanvasRenderingContext2D;

const startDrawing = (event: MouseEvent) => {
  if (!props.isInputEnabled) return;
  isDrawing = true;
  ctx.beginPath();
  ctx.moveTo(event.offsetX, event.offsetY);
};

const draw = (event: MouseEvent) => {
  if (!isDrawing || !props.isInputEnabled) return;
  ctx.lineTo(event.offsetX, event.offsetY);
  ctx.stroke();
};

const stopDrawing = () => {
  if (!isDrawing) return;
  isDrawing = false;
  ctx.closePath();
};

const clearCanvas = () => {
  if (!props.isInputEnabled) return;
  ctx.clearRect(0, 0, canvas.width, canvas.height);
};

onMounted(() => {
  canvas = document.getElementById('canvas') as HTMLCanvasElement;
  ctx = canvas.getContext('2d') as CanvasRenderingContext2D;

  resizeCanvas();

  canvas.addEventListener('mousedown', startDrawing);
  canvas.addEventListener('mousemove', draw);
  canvas.addEventListener('mouseup', stopDrawing);
  canvas.addEventListener('mouseout', stopDrawing);

  window.addEventListener('resize', resizeCanvas);
});

const resizeCanvas = () => {
  canvas.width = canvas.parentElement?.clientWidth || window.innerWidth;
  canvas.height = 250;
  ctx.fillStyle = '#f7fafc';
  ctx.fillRect(0, 0, canvas.width, canvas.height);
};

onBeforeUnmount(() => {
  window.removeEventListener('resize', resizeCanvas);
  canvas.removeEventListener('mousedown', startDrawing);
  canvas.removeEventListener('mousemove', draw);
  canvas.removeEventListener('mouseup', stopDrawing);
  canvas.removeEventListener('mouseout', stopDrawing);
});
</script>

<style scoped>
#canvas {
  background-color: #f7fafc; /* Tailwind's bg-gray-100 */
}
</style>
