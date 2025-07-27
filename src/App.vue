<template>
  <div id="app" :class="{ loaded: isLoaded }">
    <Header />
    <main class="main-content">
      <Hero id="home" />
      <About id="about" />
      <Services id="services" />
      <Contact id="contact" />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const isLoaded = ref(false)

onMounted(() => {
  isLoaded.value = true
})
</script>

<style>
/* Smooth scroll behavior for entire app */
html {
  scroll-behavior: smooth;
  font-size: 16px;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  opacity: 1;
  transition: opacity 0.5s ease-in-out;
}

.main-content {
  flex: 1;
}

/* Enhanced section transitions */
.main-content > section {
  transition: all 0.3s ease-in-out;
}

/* Improved scroll padding for fixed header */
section[id] {
  scroll-margin-top: 80px;
}

/* Enhanced Russian typography spacing */
.cyrillic-text {
  font-feature-settings: "kern" 1, "liga" 1;
  text-rendering: optimizeLegibility;
  letter-spacing: 0.02em;
  word-spacing: 0.05em;
}

/* Improved text readability for Russian content */
.cyrillic-text p,
.cyrillic-text li {
  line-height: 1.7;
  margin-bottom: 1.2em;
}

.cyrillic-text h1,
.cyrillic-text h2,
.cyrillic-text h3,
.cyrillic-text h4 {
  line-height: 1.3;
  margin-bottom: 0.8em;
}

/* Enhanced focus management for accessibility */
*:focus {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}

/* Smooth animations preference handling */
@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
  
  #app,
  .main-content > section,
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* Enhanced mobile typography */
@media (max-width: 768px) {
  html {
    font-size: 15px;
  }
  
  .cyrillic-text {
    letter-spacing: 0.01em;
    word-spacing: 0.03em;
  }
}

@media (max-width: 480px) {
  html {
    font-size: 14px;
  }
  
  section[id] {
    scroll-margin-top: 70px;
  }
}

/* Loading animation for better perceived performance */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Optional: Apply fade-in animation to sections when app is loaded */
@media (prefers-reduced-motion: no-preference) {
  #app.loaded .main-content > section {
    animation: fadeInUp 0.6s ease-out forwards;
  }

  #app.loaded .main-content > section:nth-child(1) { animation-delay: 0.05s; }
  #app.loaded .main-content > section:nth-child(2) { animation-delay: 0.1s; }
  #app.loaded .main-content > section:nth-child(3) { animation-delay: 0.15s; }
  #app.loaded .main-content > section:nth-child(4) { animation-delay: 0.2s; }
  #app.loaded .main-content > section:nth-child(5) { animation-delay: 0.25s; }
}

/* Ensure proper text selection for Russian content */
::selection {
  background-color: var(--color-primary);
  color: var(--text-primary);
}

::-moz-selection {
  background-color: var(--color-primary);
  color: var(--text-primary);
}
</style>