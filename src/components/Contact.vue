<template>
  <section class="contact" id="contact">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <h2 class="section-title cyrillic-text">Свяжитесь со мной</h2>
        <p class="section-subtitle cyrillic-text">
          Я всегда на связи, чтобы ответить на ваши вопросы и записать на сеанс
        </p>
      </div>

      <!-- Contact Actions - Left/Right Layout -->
      <div class="contact-actions">
        <h3 class="actions-title cyrillic-text">Выберите удобный способ связи</h3>
        
        <div class="contact-layout">
          <!-- Contact Buttons - Left -->
          <div class="action-buttons">
            <a href="tel:+79001234567" class="action-btn phone-btn cyrillic-text">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z" stroke="currentColor" stroke-width="2"/>
              </svg>
              <div class="btn-content">
                <span class="btn-title">Позвонить сейчас</span>
                <span class="btn-subtitle">+7 (900) 123-45-67</span>
                <span class="btn-note">Отвечаю с 9:00 до 21:00</span>
              </div>
            </a>
            
            <a href="https://wa.me/79001234567" class="action-btn whatsapp-btn cyrillic-text" target="_blank">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z" stroke="currentColor" stroke-width="2"/>
              </svg>
              <div class="btn-content">
                <span class="btn-title">WhatsApp</span>
                <span class="btn-subtitle">+7 (900) 123-45-67</span>
                <span class="btn-note">Пишите в любое время</span>
              </div>
            </a>
            
            <a href="https://t.me/lilia_massage" class="action-btn telegram-btn cyrillic-text" target="_blank">
              <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21.198 2.802a1.5 1.5 0 0 0-1.651-.219L2.603 9.125a1.5 1.5 0 0 0 .09 2.815L8.5 13.5l1.56 5.807a1.5 1.5 0 0 0 2.815.09l6.542-16.944a1.5 1.5 0 0 0-.219-1.651z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M8.5 13.5l13-13" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M14.5 6.5l-6 13" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
              <div class="btn-content">
                <span class="btn-title">Telegram</span>
                <span class="btn-subtitle">@lilia_massage</span>
                <span class="btn-note">Консультации и запись</span>
              </div>
            </a>
          </div>
          
          <!-- Info Cards - Right -->
          <div class="contact-info-cards">
            <div class="info-card">
              <h4 class="cyrillic-text">Режим работы</h4>
              <p class="cyrillic-text">Понедельник - Пятница</p>
              <p class="cyrillic-text"><strong>9:00 - 21:00</strong></p>
              <p class="cyrillic-text">Суббота - Воскресенье</p>
              <p class="cyrillic-text"><strong>10:00 - 20:00</strong></p>
            </div>
            <div class="info-card">
              <h4 class="cyrillic-text">Мой кабинет</h4>
              <p class="cyrillic-text">г. Москва</p>
              <p class="cyrillic-text">район Сокольники</p>
              <p class="cyrillic-text"><small>Точный адрес сообщу при записи</small></p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.contact {
  padding: var(--space-3xl) 0;
  background: var(--bg-secondary);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-xl);
}

/* Section Header */
.section-header {
  text-align: center;
  margin-bottom: var(--space-3xl);
}

.section-title {
  font-size: var(--font-size-4xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  margin-bottom: var(--space-md);
}

.section-subtitle {
  font-size: var(--font-size-lg);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  max-width: 600px;
  margin: 0 auto;
}

/* Contact Actions - Full Width */

/* Contact Actions */
.contact-actions {
  background: var(--bg-primary);
  padding: var(--space-3xl);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-md);
  border: 1px solid var(--color-gray-200);
  max-width: 1000px;
  margin: 0 auto;
}

.actions-title {
  font-size: var(--font-size-3xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--space-2xl);
  text-align: center;
}

/* Left/Right Layout */
.contact-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-3xl);
  align-items: center;
}

.action-buttons {
  display: flex;
  flex-direction: column;
  gap: var(--space-lg);
}

.action-btn {
  display: flex;
  align-items: center;
  gap: var(--space-md);
  padding: var(--space-lg);
  border-radius: var(--radius-lg);
  text-decoration: none;
  transition: var(--transition-normal);
  border: 2px solid transparent;
  background: var(--bg-secondary);
}

.action-btn:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
  text-decoration: none;
}

.phone-btn {
  border-color: var(--color-secondary);
  background: var(--color-secondary);
  color: var(--text-inverse);
}

.phone-btn:hover {
  background: var(--color-secondary-dark);
  border-color: var(--color-secondary-dark);
  color: var(--text-inverse);
}

.whatsapp-btn {
  border-color: #25d366;
  color: #25d366;
}

.whatsapp-btn:hover {
  background: #25d366;
  color: var(--text-inverse);
}

.telegram-btn {
  border-color: #0088cc;
  color: #0088cc;
}

.telegram-btn:hover {
  background: #0088cc;
  color: var(--text-inverse);
}

.btn-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.btn-title {
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-semibold);
  line-height: 1.2;
}

.btn-subtitle {
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-base);
  opacity: 0.9;
  margin-top: var(--space-xs);
  font-weight: var(--font-weight-medium);
}

.btn-note {
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-sm);
  opacity: 0.7;
  margin-top: var(--space-xs);
  font-style: italic;
}

/* Contact Info Cards */
.contact-info-cards {
  display: flex;
  flex-direction: column;
  gap: var(--space-lg);
}

.info-card {
  background: var(--bg-accent);
  padding: var(--space-lg);
  border-radius: var(--radius-lg);
  border: 1px solid var(--color-primary);
  text-align: center;
  transition: var(--transition-fast);
}

.info-card:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.info-card h4 {
  font-size: var(--font-size-lg);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.info-card p {
  font-size: var(--font-size-sm);
  color: var(--text-secondary);
  margin-bottom: var(--space-xs);
  line-height: var(--line-height-relaxed);
}

.info-card p:last-child {
  margin-bottom: 0;
}

.info-card small {
  font-size: var(--font-size-xs);
  opacity: 0.8;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .container {
    padding: 0 var(--space-lg);
  }
}

@media (max-width: 768px) {
  .contact {
    padding: var(--space-2xl) 0;
  }
  
  .container {
    padding: 0 var(--space-md);
  }
  
  .section-title {
    font-size: var(--font-size-3xl);
  }
  
  .section-subtitle {
    font-size: var(--font-size-base);
  }
  
  .contact-actions {
    padding: var(--space-xl);
  }
  
  .actions-title {
    font-size: var(--font-size-2xl);
  }
  
  .contact-layout {
    grid-template-columns: 1fr;
    gap: var(--space-xl);
  }
  
  .action-buttons {
    gap: var(--space-md);
  }
  
  .contact-info-cards {
    gap: var(--space-md);
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
  
  .section-title {
    font-size: var(--font-size-2xl);
  }
  
  .contact-actions {
    padding: var(--space-lg);
  }
  
  .actions-title {
    font-size: var(--font-size-xl);
  }
  
  .action-btn {
    padding: var(--space-md);
  }
  
  .btn-title {
    font-size: var(--font-size-base);
  }
}

/* Animations */
@media (prefers-reduced-motion: no-preference) {
  .action-btn,
  .info-card {
    animation: fadeInUp 0.6s ease-out forwards;
  }
  
  .action-btn:nth-child(1) { animation-delay: 0.1s; }
  .action-btn:nth-child(2) { animation-delay: 0.2s; }
  .action-btn:nth-child(3) { animation-delay: 0.3s; }
  
  .info-card:nth-child(1) { animation-delay: 0.4s; }
  .info-card:nth-child(2) { animation-delay: 0.5s; }
  .info-card:nth-child(3) { animation-delay: 0.6s; }
}
</style>