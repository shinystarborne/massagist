<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <!-- About Lilia -->
        <div class="footer-section main-info">
          <h3 class="cyrillic-text">Раца Лилия</h3>
          <p class="cyrillic-text">Персональный массажный терапевт</p>
          <p class="cyrillic-text">15 лет помогаю обрести гармонию тела и души</p>
        </div>

        <!-- Contact Info -->
        <div class="footer-section">
          <h4 class="cyrillic-text">Связь</h4>
          <div class="contact-simple">
            <p class="cyrillic-text">+7 (900) 123-45-67</p>
            <p class="cyrillic-text">г. Москва, Сокольники</p>
          </div>
        </div>

        <!-- Schedule -->
        <div class="footer-section">
          <h4 class="cyrillic-text">Режим работы</h4>
          <div class="schedule">
            <p class="cyrillic-text">Пн-Пт: 9:00-21:00</p>
            <p class="cyrillic-text">Сб-Вс: 10:00-20:00</p>
          </div>
        </div>
      </div>

      <!-- Footer Bottom -->
      <div class="footer-bottom">
        <p class="cyrillic-text">&copy; 2024 Раца Лилия</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ 
      behavior: 'smooth',
      block: 'start'
    })
  }
}
</script>

<style scoped>
.footer {
  background: var(--color-secondary);
  color: var(--text-inverse);
  padding: var(--space-xl) 0 var(--space-md);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: var(--space-2xl);
  margin-bottom: var(--space-xl);
}

.footer-section h3,
.footer-section h4 {
  margin-bottom: var(--space-md);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-inverse);
}

.footer-section p {
  margin-bottom: var(--space-sm);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-inverse);
  opacity: 0.9;
  line-height: var(--line-height-relaxed);
}

.main-info p:first-of-type {
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-medium);
  opacity: 1;
}

.contact-simple p,
.schedule p {
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-medium);
}

.footer-bottom {
  border-top: 1px solid var(--color-secondary-light);
  padding-top: var(--space-md);
  text-align: center;
}

.footer-bottom p {
  margin: 0;
  opacity: 0.7;
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-sm);
  color: var(--text-inverse);
}

/* Responsive Design */
@media (max-width: 768px) {
  .footer {
    padding: var(--space-xl) 0 var(--space-md);
  }
  
  .container {
    padding: 0 var(--space-md);
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
    text-align: center;
  }
}

@media (max-width: 480px) {
  .footer-content {
    gap: var(--space-md);
  }
  
  .footer-section h3,
  .footer-section h4 {
    font-size: var(--font-size-lg);
  }
}
</style>