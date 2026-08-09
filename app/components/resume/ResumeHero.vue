<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const dlBtn = ref<HTMLElement | null>(null);
const btnTransform = ref('translate(0, 0)');
const isPulsing = ref(true);

const MAGNET_RADIUS = 70;
const MAGNET_STRENGTH = 0.35;

function handleMouseMove(e: MouseEvent) {
  if (!dlBtn.value) return;

  const rect = dlBtn.value.getBoundingClientRect();
  const cx = rect.left + rect.width / 2;
  const cy = rect.top + rect.height / 2;
  const dx = e.clientX - cx;
  const dy = e.clientY - cy;
  const dist = Math.hypot(dx, dy);

  if (dist < MAGNET_RADIUS + rect.width / 2) {
    isPulsing.value = false;
    const pull = Math.max(0, 1 - dist / (MAGNET_RADIUS + rect.width));
    btnTransform.value = `translate(${dx * MAGNET_STRENGTH * pull}px, ${dy * MAGNET_STRENGTH * pull}dx)`;
  } else {
    btnTransform.value = 'translate(0, 0)';
    isPulsing.value = true;
  }
}

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove);
});

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove);
});
</script>

<template>
  
</template>

<style scoped>

</style>