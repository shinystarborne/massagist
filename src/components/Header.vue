<template>
  <header class="header">
    <nav class="nav">
      <div class="nav-brand">
        <h1 class="cyrillic-text">Раца Лилия</h1>
        <p class="tagline cyrillic-text">Персональный массажный терапевт</p>
      </div>
      
      <!-- Mobile hamburger button -->
      <button 
        class="mobile-menu-toggle"
        @click="toggleMobileMenu"
        :class="{ active: isMobileMenuOpen }"
        aria-label="Переключить меню"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <!-- Navigation menu -->
      <ul class="nav-menu" :class="{ active: isMobileMenuOpen }">
        <li><a href="#about" @click="scrollToSection('about')" class="cyrillic-text">Обо мне</a></li>
        <li><a href="#services" @click="scrollToSection('services')" class="cyrillic-text">Услуги и цены</a></li>
        <li><a href="#contact" @click="scrollToSection('contact')" class="cyrillic-text">Связь</a></li>
        <li class="nav-cta">
          <a href="tel:+79001234567" class="contact-btn cyrillic-text">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z" stroke="currentColor" stroke-width="2"/>
            </svg>
            Звонок
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ 
      behavior: 'smooth',
      block: 'start'
    })
  }
  // Close mobile menu after clicking
  isMobileMenuOpen.value = false
}

// Close mobile menu when clicking outside
const handleClickOutside = (event) => {
  if (!event.target.closest('.nav') && isMobileMenuOpen.value) {
    isMobileMenuOpen.value = false
  }
}

// Add event listener for clicking outside
if (typeof document !== 'undefined') {
  document.addEventListener('click', handleClickOutside)
}
</script>

<style scoped>
.header {
  background: linear-gradient(135deg, var(--color-secondary) 0%, rgba(210, 180, 140, 0.9) 100%);
  color: var(--text-inverse);
  padding: var(--space-md) 0;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
  transition: var(--transition-fast);
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-xl);
  position: relative;
}

.nav-brand {
  flex: 1;
}

.nav-brand h1 {
  margin: 0 0 var(--space-xs) 0;
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-inverse);
  line-height: var(--line-height-tight);
}

.tagline {
  margin: 0;
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  font-weight: var(--font-weight-normal);
  color: var(--color-primary-light);
  opacity: 0.9;
}

/* Mobile hamburger menu button */
.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: var(--space-sm);
  z-index: 1002;
  position: relative;
}

.mobile-menu-toggle span {
  width: 25px;
  height: 3px;
  background: var(--text-inverse);
  margin: 3px 0;
  transition: var(--transition-normal);
  border-radius: 2px;
}

.mobile-menu-toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.mobile-menu-toggle.active span:nth-child(2) {
  opacity: 0;
}

.mobile-menu-toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* Navigation menu */
.nav-menu {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: var(--space-lg);
}

.nav-menu li {
  position: relative;
}

.nav-menu a {
  color: var(--text-inverse);
  text-decoration: none;
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-base);
  transition: var(--transition-fast);
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--radius-md);
  position: relative;
  display: inline-block;
}

.nav-menu a:hover {
  background: var(--color-primary);
  color: var(--text-primary);
  transform: translateY(-1px);
}

.nav-menu a:active {
  transform: translateY(0);
}

/* Contact CTA Button */
.nav-cta {
  margin-left: var(--space-md);
}

.contact-btn {
  background: var(--color-primary) !important;
  color: var(--text-primary) !important;
  padding: var(--space-sm) var(--space-md) !important;
  border: 2px solid var(--color-primary-dark) !important;
  border-radius: var(--radius-lg) !important;
  font-weight: var(--font-weight-semibold) !important;
  display: inline-flex !important;
  align-items: center !important;
  gap: var(--space-xs) !important;
  transition: var(--transition-fast) !important;
  text-decoration: none !important;
}

.contact-btn:hover {
  background: var(--color-primary-dark) !important;
  color: var(--text-primary) !important;
  transform: translateY(-2px) !important;
  box-shadow: var(--shadow-md) !important;
  text-decoration: none !important;
}

.contact-btn svg {
  flex-shrink: 0;
}

/* Mobile responsive design */
@media (max-width: 768px) {
  .nav {
    padding: 0 var(--space-md);
    position: relative;
    z-index: 1003;
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
  
  .nav-menu {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(107, 142, 35, 0.95);
    backdrop-filter: blur(10px);
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: var(--space-xl);
    padding: var(--space-3xl);
    transform: translateX(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease-in-out;
    z-index: 1001;
  }
  
  .nav-menu.active {
    transform: translateX(0);
    opacity: 1;
    visibility: visible;
  }
  
  .nav-menu li {
    margin: 0;
  }
  
  .nav-menu a {
    display: block;
    padding: var(--space-lg) var(--space-xl);
    border-radius: var(--radius-lg);
    margin-bottom: 0;
    text-align: center;
    border: 2px solid rgba(255, 255, 255, 0.2);
    font-size: var(--font-size-lg);
    min-width: 200px;
    backdrop-filter: blur(5px);
    background: rgba(255, 255, 255, 0.1);
  }
  
  .nav-menu a:hover {
    background: rgba(255, 255, 255, 0.3);
    border-color: rgba(255, 255, 255, 0.5);
    transform: scale(1.05);
  }
  
  .nav-cta {
    margin-left: 0;
    margin-top: var(--space-lg);
  }
  
  .contact-btn {
    width: 100% !important;
    justify-content: center !important;
    padding: var(--space-md) !important;
  }
  
  .nav-brand h1 {
    font-size: var(--font-size-xl);
  }
  
  .tagline {
    font-size: var(--font-size-xs);
  }
}

@media (max-width: 480px) {
  .nav {
    padding: 0 var(--space-sm);
  }
  
  .nav-brand h1 {
    font-size: var(--font-size-lg);
  }
  
  .tagline {
    display: none;
  }
}

/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Enhanced focus states for accessibility */
.nav-menu a:focus {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}

.mobile-menu-toggle:focus {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}
</style>