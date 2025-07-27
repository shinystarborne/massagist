<template>
  <section class="hero" id="home">
    <!-- Floating Elements -->
    <div class="floating-elements">
      <div class="floating-circle floating-circle-1"></div>
      <div class="floating-circle floating-circle-2"></div>
      <div class="floating-circle floating-circle-3"></div>
      <div class="floating-circle floating-circle-4"></div>
    </div>
    
    <div class="hero-content">
      <div class="hero-text">
        <h1 class="hero-headline cyrillic-text">
          Верните телу легкость и гармонию
        </h1>
        <p class="hero-tagline cyrillic-text">
          Я Лилия, и моя миссия — помочь вам почувствовать себя лучше через силу целебного прикосновения
        </p>
        <div class="hero-features">
          <span class="feature cyrillic-text">15+ лет опыта</span>
          <span class="feature cyrillic-text">Персональный подход</span>
          <span class="feature cyrillic-text">Уютная домашняя атмосфера</span>
        </div>
      </div>
      <div class="hero-action">
        <button class="cta-button cyrillic-text" @click="scrollToContact">
          Связаться со мной
        </button>
        <p class="cta-note cyrillic-text">
          Первая консультация и диагностика бесплатно
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToContact = () => {
  const element = document.getElementById('contact')
  if (element) {
    element.scrollIntoView({ 
      behavior: 'smooth',
      block: 'start'
    })
  }
}
</script>

<style scoped>
.hero {
  background: var(--bg-primary);
  padding: var(--space-3xl) var(--space-xl);
  min-height: 80vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 80%, rgba(210, 180, 140, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(107, 142, 35, 0.1) 0%, transparent 50%),
    linear-gradient(135deg, rgba(210, 180, 140, 0.03) 0%, rgba(107, 142, 35, 0.05) 100%);
  z-index: 1;
  animation: gradientShift 8s ease-in-out infinite;
}

@keyframes gradientShift {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.8; }
}

/* Floating Elements */
.floating-elements {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  z-index: 1;
}

.floating-circle {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(45deg, rgba(210, 180, 140, 0.1), rgba(107, 142, 35, 0.1));
  animation: float 20s ease-in-out infinite;
}

.floating-circle-1 {
  width: 60px;
  height: 60px;
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.floating-circle-2 {
  width: 80px;
  height: 80px;
  top: 60%;
  right: 15%;
  animation-delay: -5s;
}

.floating-circle-3 {
  width: 40px;
  height: 40px;
  top: 80%;
  left: 20%;
  animation-delay: -10s;
}

.floating-circle-4 {
  width: 100px;
  height: 100px;
  top: 30%;
  right: 25%;
  animation-delay: -15s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px) rotate(0deg);
    opacity: 0.7;
  }
  25% {
    transform: translateY(-20px) rotate(90deg);
    opacity: 0.9;
  }
  50% {
    transform: translateY(-40px) rotate(180deg);
    opacity: 0.5;
  }
  75% {
    transform: translateY(-20px) rotate(270deg);
    opacity: 0.8;
  }
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  gap: var(--space-2xl);
}

.hero-text {
  margin-bottom: var(--space-xl);
}

.hero-headline {
  font-size: var(--font-size-5xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  line-height: var(--line-height-tight);
  margin-bottom: var(--space-lg);
  letter-spacing: -0.02em;
}

.hero-tagline {
  font-size: var(--font-size-xl);
  font-family: 'Open Sans', sans-serif;
  font-weight: var(--font-weight-normal);
  color: var(--text-secondary);
  line-height: var(--line-height-relaxed);
  margin-bottom: var(--space-xl);
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.hero-features {
  display: flex;
  justify-content: center;
  gap: var(--space-lg);
  flex-wrap: wrap;
  margin-bottom: var(--space-xl);
}

.feature {
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-medium);
  color: var(--color-secondary);
  background: var(--bg-accent);
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--radius-xl);
  border: 1px solid var(--color-primary);
  white-space: nowrap;
  transition: var(--transition-fast);
}

.feature:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.hero-action {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-md);
}

.cta-button {
  background: var(--color-secondary);
  color: var(--text-inverse);
  padding: var(--space-md) var(--space-2xl);
  border: none;
  border-radius: var(--radius-xl);
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
  transition: var(--transition-normal);
  box-shadow: var(--shadow-md);
  min-width: 240px;
  position: relative;
  overflow: hidden;
}

.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.2),
    transparent
  );
  transition: left 0.5s;
}

.cta-button:hover::before {
  left: 100%;
}

.cta-button:hover {
  background: var(--color-secondary-dark);
  transform: translateY(-3px);
  box-shadow: var(--shadow-lg);
}

.cta-button:active {
  transform: translateY(-1px);
}

.cta-note {
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-sm);
  color: var(--text-muted);
  margin: 0;
  font-style: italic;
}

/* Responsive design */
@media (max-width: 1024px) {
  .hero {
    min-height: 70vh;
    padding: var(--space-2xl) var(--space-lg);
  }
  
  .hero-headline {
    font-size: var(--font-size-4xl);
  }
  
  .hero-tagline {
    font-size: var(--font-size-lg);
  }
}

@media (max-width: 768px) {
  .hero {
    min-height: 60vh;
    padding: var(--space-2xl) var(--space-md);
  }
  
  .hero-content {
    gap: var(--space-xl);
  }
  
  .hero-headline {
    font-size: var(--font-size-3xl);
  }
  
  .hero-tagline {
    font-size: var(--font-size-base);
  }
  
  .hero-features {
    flex-direction: column;
    align-items: center;
    gap: var(--space-sm);
  }
  
  .feature {
    font-size: var(--font-size-xs);
    padding: var(--space-xs) var(--space-sm);
  }
  
  .cta-button {
    padding: var(--space-sm) var(--space-xl);
    font-size: var(--font-size-base);
    min-width: 200px;
  }
}

@media (max-width: 480px) {
  .hero {
    min-height: 50vh;
    padding: var(--space-xl) var(--space-sm);
  }
  
  .hero-headline {
    font-size: var(--font-size-2xl);
    line-height: 1.3;
  }
  
  .hero-tagline {
    font-size: var(--font-size-sm);
  }
  
  .cta-button {
    padding: var(--space-sm) var(--space-lg);
    font-size: var(--font-size-sm);
    min-width: 180px;
  }
  
  .cta-note {
    font-size: var(--font-size-xs);
  }
}

/* Focus states for accessibility */
.cta-button:focus {
  outline: 3px solid var(--color-primary);
  outline-offset: 3px;
}

/* Smooth animations */
@media (prefers-reduced-motion: no-preference) {
  .hero-headline,
  .hero-tagline,
  .hero-features,
  .hero-action {
    animation: fadeInUp 0.8s ease-out forwards;
  }
  
  .hero-tagline {
    animation-delay: 0.2s;
  }
  
  .hero-features {
    animation-delay: 0.4s;
  }
  
  .hero-action {
    animation-delay: 0.6s;
  }
}

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
</style>