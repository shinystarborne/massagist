<template>
  <Transition name="back-to-top">
    <button 
      v-if="isVisible"
      class="back-to-top-btn"
      @click="scrollToTop"
      aria-label="Наверх"
    >
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M7 14l5-5 5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </button>
  </Transition>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isVisible = ref(false)

const handleScroll = () => {
  isVisible.value = window.pageYOffset > 300
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.back-to-top-btn {
  position: fixed;
  bottom: var(--space-xl);
  right: var(--space-xl);
  width: 56px;
  height: 56px;
  background: linear-gradient(135deg, var(--color-secondary), var(--color-primary));
  color: var(--text-inverse);
  border: none;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: 0 4px 20px rgba(107, 142, 35, 0.3);
  transition: var(--transition-normal);
  z-index: 1000;
  backdrop-filter: blur(10px);
}

.back-to-top-btn:hover {
  transform: translateY(-4px) scale(1.1);
  box-shadow: 0 8px 30px rgba(107, 142, 35, 0.5);
  background: linear-gradient(135deg, var(--color-secondary-dark), var(--color-primary-dark));
}

.back-to-top-btn:active {
  transform: translateY(-2px) scale(1.05);
}

.back-to-top-btn svg {
  transition: var(--transition-fast);
}

.back-to-top-btn:hover svg {
  transform: translateY(-2px);
}

/* Floating animation */
.back-to-top-btn {
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
}

.back-to-top-btn:hover {
  animation: none;
}

/* Transition animations */
.back-to-top-enter-active,
.back-to-top-leave-active {
  transition: all 0.3s ease;
}

.back-to-top-enter-from {
  opacity: 0;
  transform: translateY(100px) scale(0.8);
}

.back-to-top-leave-to {
  opacity: 0;
  transform: translateY(100px) scale(0.8);
}

/* Responsive design */
@media (max-width: 768px) {
  .back-to-top-btn {
    bottom: var(--space-lg);
    right: var(--space-lg);
    width: 48px;
    height: 48px;
  }
}

@media (max-width: 480px) {
  .back-to-top-btn {
    bottom: var(--space-md);
    right: var(--space-md);
    width: 44px;
    height: 44px;
  }
}

/* Focus state for accessibility */
.back-to-top-btn:focus {
  outline: 3px solid var(--color-primary);
  outline-offset: 3px;
}
</style>