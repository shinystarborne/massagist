<template>
  <div class="scroll-progress" :style="{ width: `${scrollPercentage}%` }"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrollPercentage = ref(0)

const updateScrollProgress = () => {
  const scrollTop = window.pageYOffset || document.documentElement.scrollTop
  const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight
  scrollPercentage.value = (scrollTop / scrollHeight) * 100
}

onMounted(() => {
  window.addEventListener('scroll', updateScrollProgress)
  updateScrollProgress()
})

onUnmounted(() => {
  window.removeEventListener('scroll', updateScrollProgress)
})
</script>

<style scoped>
.scroll-progress {
  position: fixed;
  top: 0;
  left: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--color-secondary), var(--color-primary));
  z-index: 9999;
  transition: width 0.1s ease-out;
  box-shadow: 0 2px 10px rgba(107, 142, 35, 0.3);
}

.scroll-progress::after {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 20px;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.8));
  animation: shine 2s ease-in-out infinite;
}

@keyframes shine {
  0%, 100% { opacity: 0; }
  50% { opacity: 1; }
}
</style>