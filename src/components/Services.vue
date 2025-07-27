<template>
  <section class="services" id="services">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <h2 class="section-title cyrillic-text">Мои услуги и цены</h2>
        <p class="section-subtitle cyrillic-text">
          Техники массажа, которые я освоила за годы практики, с прозрачными ценами
        </p>
      </div>

      <!-- Services Grid -->
      <div class="services-grid">
        <div 
          class="service-card" 
          v-for="(service, index) in services" 
          :key="service.id"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <!-- Service Icon -->
          <div class="service-icon" v-html="service.icon"></div>
          
          <!-- Service Content -->
          <div class="service-content">
            <h3 class="service-name cyrillic-text">{{ service.name }}</h3>
            <p class="service-description cyrillic-text">{{ service.description }}</p>
            
            <!-- Service Features -->
            <ul class="service-features">
              <li v-for="feature in service.features" :key="feature" class="cyrillic-text">
                {{ feature }}
              </li>
            </ul>
            
            <!-- Duration & Price -->
            <div class="service-details">
              <div class="duration cyrillic-text">
                <span class="duration-label">Продолжительность:</span>
                <span class="duration-value">{{ service.duration }}</span>
              </div>
              <div class="price">
                <span class="price-value">{{ service.price }}</span>
                <span class="price-currency cyrillic-text">руб.</span>
              </div>
            </div>
          </div>
          
          <!-- Book Button -->
          <button class="book-button cyrillic-text" @click="bookService">
            Связаться со мной
          </button>
        </div>
      </div>

      <!-- Additional Services Note -->
      <div class="additional-info">
        <p class="info-text cyrillic-text">
          * Все цены указаны за стандартный сеанс. Доступны пакетные предложения и индивидуальные программы.
        </p>
        <p class="info-text cyrillic-text">
          Первая консультация включает оценку состояния и подбор оптимального вида массажа.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Service Icons as SVG strings
const icons = {
  swedish: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M12 2L13.09 8.26L22 9L13.09 9.74L12 16L10.91 9.74L2 9L10.91 8.26L12 2Z" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <circle cx="12" cy="12" r="3" stroke="currentColor" stroke-width="2"/>
  </svg>`,
  
  deepTissue: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M12 2L2 7L12 12L22 7L12 2Z" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <path d="M2 17L12 22L22 17" stroke="currentColor" stroke-width="2"/>
    <path d="M2 12L12 17L22 12" stroke="currentColor" stroke-width="2"/>
  </svg>`,
  
  hotStone: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <ellipse cx="12" cy="18" rx="6" ry="3" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <ellipse cx="12" cy="12" rx="4" ry="2" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.3"/>
    <ellipse cx="12" cy="6" rx="2" ry="1" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.4"/>
  </svg>`,
  
  thai: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2Z" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <path d="M21 9V7L15 9L13.5 7.5C13.1 7.1 12.6 6.9 12 6.9S10.9 7.1 10.5 7.5L9 9L3 7V9L9 10L10.4 22H13.6L15 10L21 9Z" stroke="currentColor" stroke-width="2"/>
  </svg>`,
  
  aromatic: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M12 2L12 12M12 12L8 8M12 12L16 8" stroke="currentColor" stroke-width="2"/>
    <circle cx="12" cy="17" r="4" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <path d="M8 21H16" stroke="currentColor" stroke-width="2"/>
  </svg>`,
  
  reflexology: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M8 21V19C8 18.4 8.4 18 9 18H15C15.6 18 16 18.4 16 19V21" stroke="currentColor" stroke-width="2"/>
    <path d="M9 18V16C9 14.9 9.9 14 11 14H13C14.1 14 15 14.9 15 16V18" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <circle cx="12" cy="8" r="4" stroke="currentColor" stroke-width="2"/>
    <path d="M12 4V2" stroke="currentColor" stroke-width="2"/>
    <path d="M16.2 5.8L17.6 4.4" stroke="currentColor" stroke-width="2"/>
    <path d="M7.8 5.8L6.4 4.4" stroke="currentColor" stroke-width="2"/>
  </svg>`,
  
  weeklyPackage: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <rect x="3" y="4" width="18" height="15" rx="2" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.1"/>
    <path d="M8 2v4M16 2v4" stroke="currentColor" stroke-width="2"/>
    <path d="M3 10h18" stroke="currentColor" stroke-width="2"/>
    <circle cx="8" cy="14" r="1" fill="currentColor"/>
    <circle cx="12" cy="14" r="1" fill="currentColor"/>
    <circle cx="16" cy="14" r="1" fill="currentColor"/>
  </svg>`,
  
  monthlyPackage: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M12 2L15.09 8.26L22 9L15.09 9.74L12 16L8.91 9.74L2 9L8.91 8.26L12 2Z" stroke="currentColor" stroke-width="2" fill="currentColor" opacity="0.2"/>
    <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" stroke="currentColor" stroke-width="2"/>
    <path d="M12 8v4l3 3" stroke="currentColor" stroke-width="2"/>
  </svg>`
}

const services = ref([
  {
    id: 1,
    name: 'Шведский массаж',
    description: 'Классическая расслабляющая техника с длинными плавными движениями для снятия стресса и общего оздоровления.',
    features: ['Улучшение кровообращения', 'Снятие мышечного напряжения', 'Глубокое расслабление'],
    duration: '60 минут',
    price: '3500',
    icon: icons.swedish
  },
  {
    id: 2,
    name: 'Глубокий тканевый массаж',
    description: 'Интенсивная терапия для работы с глубокими мышцами, устранения хронических болей и мышечных спазмов.',
    features: ['Работа с триггерными точками', 'Снятие хронических болей', 'Восстановление подвижности'],
    duration: '60 минут',
    price: '4000',
    icon: icons.deepTissue
  },
  {
    id: 3,
    name: 'Массаж горячими камнями',
    description: 'Терапевтический массаж с использованием нагретых базальтовых камней для глубокого прогрева и расслабления.',
    features: ['Глубокий прогрев мышц', 'Улучшение метаболизма', 'Снятие энергетических блоков'],
    duration: '75 минут',
    price: '4500',
    icon: icons.hotStone
  },
  {
    id: 4,
    name: 'Тайский массаж',
    description: 'Древняя техника, сочетающая элементы йоги, акупрессуры и растяжки для восстановления энергетического баланса.',
    features: ['Увеличение гибкости', 'Энергетическое восстановление', 'Работа с чакрами'],
    duration: '90 минут',
    price: '5000',
    icon: icons.thai
  },
  {
    id: 5,
    name: 'Ароматерапевтический массаж',
    description: 'Расслабляющий массаж с использованием натуральных эфирных масел для воздействия на эмоциональное состояние.',
    features: ['Ароматерапия', 'Эмоциональное восстановление', 'Улучшение настроения'],
    duration: '60 минут',
    price: '3800',
    icon: icons.aromatic
  },
  {
    id: 6,
    name: 'Рефлексотерапия стоп',
    description: 'Специализированный массаж стоп, воздействующий на рефлекторные точки, связанные с различными органами.',
    features: ['Активация рефлекторных точек', 'Общее оздоровление', 'Улучшение кровообращения'],
    duration: '45 минут',
    price: '2800',
    icon: icons.reflexology
  }
])

const bookService = () => {
  // Scroll to contact section
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
.services {
  padding: var(--space-3xl) 0;
  background: 
    radial-gradient(circle at 10% 20%, rgba(210, 180, 140, 0.03) 0%, transparent 50%),
    radial-gradient(circle at 90% 80%, rgba(107, 142, 35, 0.03) 0%, transparent 50%),
    var(--bg-secondary);
  position: relative;
  overflow: hidden;
}

.services::before {
  content: '';
  position: absolute;
  top: 0;
  left: -50%;
  width: 200%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(210, 180, 140, 0.02), transparent);
  animation: shimmer 15s linear infinite;
  z-index: 0;
}

@keyframes shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-xl);
  position: relative;
  z-index: 1;
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

/* Services Grid */
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-xl);
  margin-bottom: var(--space-2xl);
}

/* Service Card */
.service-card {
  background: var(--bg-primary);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-md);
  border: 1px solid var(--color-gray-200);
  overflow: hidden;
  transition: var(--transition-normal);
  display: flex;
  flex-direction: column;
  position: relative;
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--color-secondary), var(--color-primary));
  transform: scaleX(0);
  transition: var(--transition-normal);
  transform-origin: left;
}

.service-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
  border-color: var(--color-primary);
  background: linear-gradient(135deg, var(--bg-primary) 0%, rgba(210, 180, 140, 0.05) 100%);
}

.service-card:hover::before {
  transform: scaleX(1);
}

/* Service Icon */
.service-icon {
  padding: var(--space-xl) var(--space-xl) var(--space-md);
  display: flex;
  justify-content: center;
  color: var(--color-secondary);
  transition: var(--transition-normal);
}

.service-card:hover .service-icon {
  color: var(--color-secondary-dark);
  transform: scale(1.1);
}

/* Service Content */
.service-content {
  padding: 0 var(--space-xl);
  flex: 1;
  display: flex;
  flex-direction: column;
}

.service-name {
  font-size: var(--font-size-xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  margin-bottom: var(--space-md);
  text-align: center;
  min-height: 3.2em;
  display: flex;
  align-items: center;
  justify-content: center;
  line-height: 1.3;
}

.service-description {
  font-size: var(--font-size-base);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-secondary);
  margin-bottom: var(--space-lg);
  text-align: center;
  min-height: 4.8em;
  display: flex;
  align-items: center;
}

/* Service Features */
.service-features {
  list-style: none;
  padding: 0;
  margin: 0 0 var(--space-lg) 0;
  min-height: 7.5em;
  flex: 1;
}

.service-features li {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  padding: var(--space-xs) 0;
  position: relative;
  padding-left: var(--space-lg);
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: var(--font-weight-bold);
}

/* Service Details */
.service-details {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--space-md);
  background: var(--bg-accent);
  border-radius: var(--radius-lg);
  margin-bottom: var(--space-lg);
}

.duration {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.duration-label {
  font-size: var(--font-size-xs);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.duration-value {
  font-size: var(--font-size-sm);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
}

.price {
  display: flex;
  align-items: baseline;
  gap: var(--space-xs);
}

.price-value {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--color-secondary);
}

.price-currency {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
}

/* Book Button */
.book-button {
  background: var(--color-secondary);
  color: var(--text-inverse);
  border: none;
  padding: var(--space-md) var(--space-xl);
  margin: 0 var(--space-xl) var(--space-xl);
  border-radius: var(--radius-lg);
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-base);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
  transition: var(--transition-normal);
  position: relative;
  overflow: hidden;
}

.book-button::before {
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
  transition: left 0.6s;
}

.book-button:hover::before {
  left: 100%;
}

.book-button:hover {
  background: var(--color-secondary-dark);
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.book-button:active {
  transform: translateY(0);
}

/* Additional Info */
.additional-info {
  background: var(--bg-primary);
  padding: var(--space-xl);
  border-radius: var(--radius-lg);
  border: 1px solid var(--color-gray-200);
  text-align: center;
  margin-top: var(--space-2xl);
}

.info-text {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-muted);
  margin-bottom: var(--space-sm);
}

.info-text:last-child {
  margin-bottom: 0;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .container {
    padding: 0 var(--space-lg);
  }
  
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: var(--space-lg);
  }
}

@media (max-width: 768px) {
  .services {
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
  
  .services-grid {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
  }
  
  .service-card {
    margin: 0 var(--space-sm);
  }
  
  .service-details {
    flex-direction: column;
    gap: var(--space-sm);
    text-align: center;
  }
  
  .price {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
  
  .section-title {
    font-size: var(--font-size-2xl);
  }
  
  .service-card {
    margin: 0;
  }
  
  .service-icon {
    padding: var(--space-lg) var(--space-lg) var(--space-sm);
  }
  
  .service-content {
    padding: 0 var(--space-lg);
  }
  
  .service-name {
    font-size: var(--font-size-lg);
    min-height: 3.6em;
  }
  
  .service-description {
    min-height: 5.4em;
  }
  
  .service-features {
    min-height: 8.5em;
  }
  
  .book-button {
    margin: 0 var(--space-lg) var(--space-lg);
    padding: var(--space-sm) var(--space-lg);
  }
}

/* Animations */
@media (prefers-reduced-motion: no-preference) {
  .service-card {
    animation: fadeInUp 0.6s ease-out forwards;
    opacity: 0;
  }
  
  .service-card:nth-child(1) { animation-delay: 0s; }
  .service-card:nth-child(2) { animation-delay: 0.1s; }
  .service-card:nth-child(3) { animation-delay: 0.2s; }
  .service-card:nth-child(4) { animation-delay: 0.3s; }
  .service-card:nth-child(5) { animation-delay: 0.4s; }
  .service-card:nth-child(6) { animation-delay: 0.5s; }
}

/* Focus states for accessibility */
.book-button:focus {
  outline: 3px solid var(--color-primary);
  outline-offset: 2px;
}
</style>