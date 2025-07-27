<template>
  <section class="pricing" id="prices">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <h2 class="section-title cyrillic-text">Цены на услуги</h2>
        <p class="section-subtitle cyrillic-text">
          Доступные цены на профессиональный массаж высокого качества
        </p>
      </div>

      <!-- Pricing Table -->
      <div class="pricing-content">
        <!-- Main Services Table -->
        <div class="pricing-table">
          <div class="table-header">
            <h3 class="cyrillic-text">Основные услуги</h3>
          </div>
          
          <div class="table-body">
            <div 
              class="pricing-row" 
              v-for="(service, index) in mainServices" 
              :key="service.id"
              :style="{ animationDelay: `${index * 0.1}s` }"
            >
              <div class="service-info">
                <h4 class="service-name cyrillic-text">{{ service.name }}</h4>
                <p class="service-description cyrillic-text">{{ service.description }}</p>
                <div class="service-features">
                  <span 
                    v-for="feature in service.features" 
                    :key="feature" 
                    class="feature-tag cyrillic-text"
                  >
                    {{ feature }}
                  </span>
                </div>
              </div>
              
              <div class="pricing-info">
                <div class="duration cyrillic-text">
                  <span class="duration-value">{{ service.duration }}</span>
                </div>
                <div class="price">
                  <span class="price-value">{{ service.price }}</span>
                  <span class="price-currency cyrillic-text">руб.</span>
                </div>
                <button class="book-btn cyrillic-text" @click="scrollToContact">
                  Записаться
                </button>
              </div>
            </div>
          </div>
        </div>

        <!-- Package Deals -->
        <div class="package-deals">
          <h3 class="package-title cyrillic-text">Пакетные предложения</h3>
          <div class="packages-grid">
            <div 
              class="package-card" 
              v-for="(pkg, index) in packages" 
              :key="pkg.id"
              :class="{ 'featured': pkg.featured }"
              :style="{ animationDelay: `${(index + mainServices.length) * 0.1}s` }"
            >
              <div class="package-header">
                <h4 class="package-name cyrillic-text">{{ pkg.name }}</h4>
                <div class="package-badge cyrillic-text" v-if="pkg.featured">
                  Популярный
                </div>
              </div>
              
              <div class="package-content">
                <p class="package-description cyrillic-text">{{ pkg.description }}</p>
                <ul class="package-includes">
                  <li v-for="item in pkg.includes" :key="item" class="cyrillic-text">
                    {{ item }}
                  </li>
                </ul>
                
                <div class="package-pricing">
                  <div class="original-price cyrillic-text" v-if="pkg.originalPrice">
                    <span class="crossed-out">{{ pkg.originalPrice }} руб.</span>
                  </div>
                  <div class="package-price">
                    <span class="price-value">{{ pkg.price }}</span>
                    <span class="price-currency cyrillic-text">руб.</span>
                  </div>
                  <div class="savings cyrillic-text" v-if="pkg.savings">
                    Экономия: {{ pkg.savings }} руб.
                  </div>
                </div>
              </div>
              
              <button class="package-btn cyrillic-text" @click="scrollToContact">
                Выбрать пакет
              </button>
            </div>
          </div>
        </div>

        <!-- Additional Information -->
        <div class="pricing-info-section">
          <div class="info-cards">
            <div class="info-card">
              <div class="info-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Первая консультация</h4>
              <p class="cyrillic-text">Бесплатная оценка состояния и подбор оптимального вида массажа</p>
            </div>
            
            <div class="info-card">
              <div class="info-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
                  <path d="M12 6v6l4 2" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Гибкое расписание</h4>
              <p class="cyrillic-text">Работаем 7 дней в неделю с 9:00 до 21:00, включая выходные</p>
            </div>
            
            <div class="info-card">
              <div class="info-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M16 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2" stroke="currentColor" stroke-width="2"/>
                  <circle cx="8.5" cy="7" r="4" stroke="currentColor" stroke-width="2"/>
                  <path d="M20 8v6M23 11h-6" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Скидки постоянным клиентам</h4>
              <p class="cyrillic-text">Накопительная система скидок до 15% для регулярных посетителей</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const mainServices = ref([
  {
    id: 1,
    name: 'Шведский массаж',
    description: 'Классическая расслабляющая техника с длинными плавными движениями',
    features: ['Расслабление', 'Антистресс', 'Улучшение кровообращения'],
    duration: '60 минут',
    price: '3500'
  },
  {
    id: 2,
    name: 'Глубокий тканевый массаж',
    description: 'Интенсивная терапия для работы с глубокими мышцами',
    features: ['Снятие боли', 'Работа с спазмами', 'Восстановление'],
    duration: '60 минут',
    price: '4000'
  },
  {
    id: 3,
    name: 'Массаж горячими камнями',
    description: 'Терапевтический массаж с нагретыми базальтовыми камнями',
    features: ['Глубокий прогрев', 'Детоксикация', 'Релаксация'],
    duration: '75 минут',
    price: '4500'
  },
  {
    id: 4,
    name: 'Тайский массаж',
    description: 'Древняя техника с элементами йоги и растяжки',
    features: ['Гибкость', 'Энергия', 'Баланс'],
    duration: '90 минут',
    price: '5000'
  },
  {
    id: 5,
    name: 'Ароматерапевтический массаж',
    description: 'Расслабляющий массаж с натуральными эфирными маслами',
    features: ['Ароматерапия', 'Настроение', 'Релаксация'],
    duration: '60 минут',
    price: '3800'
  },
  {
    id: 6,
    name: 'Рефлексотерапия стоп',
    description: 'Специализированный массаж рефлекторных точек стоп',
    features: ['Рефлекторные точки', 'Оздоровление', 'Профилактика'],
    duration: '45 минут',
    price: '2800'
  }
])

const packages = ref([
  {
    id: 1,
    name: 'Базовый пакет',
    description: 'Идеальный выбор для знакомства с нашими услугами',
    includes: ['3 сеанса шведского массажа', 'Бесплатная консультация', 'Гибкое расписание'],
    originalPrice: '10500',
    price: '9500',
    savings: '1000',
    featured: false
  },
  {
    id: 2,
    name: 'Премиум пакет',
    description: 'Комплексная программа для полного восстановления',
    includes: ['5 сеансов на выбор', '1 сеанс горячими камнями', 'Ароматерапия в подарок', 'Скидка 15%'],
    originalPrice: '20000',
    price: '17000',
    savings: '3000',
    featured: true
  },
  {
    id: 3,
    name: 'VIP пакет',
    description: 'Эксклюзивная программа для требовательных клиентов',
    includes: ['10 сеансов любых видов массажа', 'Персональный массажист', 'Гибкое расписание', 'Скидка 20%'],
    originalPrice: '40000',
    price: '32000',
    savings: '8000',
    featured: false
  }
])

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
.pricing {
  padding: var(--space-3xl) 0;
  background: var(--bg-primary);
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

/* Pricing Content */
.pricing-content {
  display: flex;
  flex-direction: column;
  gap: var(--space-3xl);
}

/* Pricing Table */
.pricing-table {
  background: var(--bg-secondary);
  border-radius: var(--radius-xl);
  overflow: hidden;
  box-shadow: var(--shadow-md);
}

.table-header {
  background: var(--color-secondary);
  color: var(--text-inverse);
  padding: var(--space-lg);
  text-align: center;
}

.table-header h3 {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  margin: 0;
}

.table-body {
  padding: var(--space-lg);
}

.pricing-row {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: var(--space-xl);
  padding: var(--space-lg);
  background: var(--bg-primary);
  border-radius: var(--radius-lg);
  margin-bottom: var(--space-md);
  border: 1px solid var(--color-gray-200);
  transition: var(--transition-normal);
  align-items: center;
}

.pricing-row:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
  border-color: var(--color-primary);
}

.pricing-row:last-child {
  margin-bottom: 0;
}

.service-info {
  flex: 1;
}

.service-name {
  font-size: var(--font-size-xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.service-description {
  font-size: var(--font-size-base);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  margin-bottom: var(--space-md);
  line-height: var(--line-height-relaxed);
}

.service-features {
  display: flex;
  gap: var(--space-sm);
  flex-wrap: wrap;
}

.feature-tag {
  background: var(--bg-accent);
  color: var(--color-secondary);
  padding: var(--space-xs) var(--space-sm);
  border-radius: var(--radius-sm);
  font-size: var(--font-size-xs);
  font-family: 'Open Sans', sans-serif;
  font-weight: var(--font-weight-medium);
  border: 1px solid var(--color-primary);
}

.pricing-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-sm);
  text-align: center;
  min-width: 150px;
}

.duration {
  font-size: var(--font-size-sm);
  color: var(--text-muted);
  font-family: 'Open Sans', sans-serif;
}

.price {
  display: flex;
  align-items: baseline;
  gap: var(--space-xs);
  margin-bottom: var(--space-sm);
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

.book-btn {
  background: var(--color-secondary);
  color: var(--text-inverse);
  border: none;
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--radius-md);
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
  transition: var(--transition-normal);
  min-width: 120px;
}

.book-btn:hover {
  background: var(--color-secondary-dark);
  transform: translateY(-1px);
}

/* Package Deals */
.package-deals {
  margin-top: var(--space-2xl);
}

.package-title {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  text-align: center;
  margin-bottom: var(--space-xl);
}

.packages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--space-xl);
}

.package-card {
  background: var(--bg-primary);
  border-radius: var(--radius-xl);
  border: 2px solid var(--color-gray-200);
  overflow: hidden;
  transition: var(--transition-normal);
  position: relative;
}

.package-card.featured {
  border-color: var(--color-secondary);
  transform: scale(1.05);
}

.package-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-xl);
}

.package-card.featured:hover {
  transform: scale(1.05) translateY(-4px);
}

.package-header {
  background: var(--bg-accent);
  padding: var(--space-lg);
  text-align: center;
  position: relative;
}

.package-card.featured .package-header {
  background: var(--color-secondary);
  color: var(--text-inverse);
}

.package-name {
  font-size: var(--font-size-xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  margin: 0;
}

.package-badge {
  position: absolute;
  top: -10px;
  right: var(--space-md);
  background: var(--color-primary);
  color: var(--text-primary);
  padding: var(--space-xs) var(--space-sm);
  border-radius: var(--radius-sm);
  font-size: var(--font-size-xs);
  font-weight: var(--font-weight-semibold);
  transform: rotate(15deg);
}

.package-content {
  padding: var(--space-xl);
}

.package-description {
  font-size: var(--font-size-base);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  margin-bottom: var(--space-lg);
  text-align: center;
}

.package-includes {
  list-style: none;
  padding: 0;
  margin: 0 0 var(--space-lg) 0;
}

.package-includes li {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  padding: var(--space-xs) 0;
  position: relative;
  padding-left: var(--space-lg);
}

.package-includes li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: var(--font-weight-bold);
}

.package-pricing {
  text-align: center;
  margin-bottom: var(--space-lg);
}

.original-price {
  margin-bottom: var(--space-xs);
}

.crossed-out {
  text-decoration: line-through;
  color: var(--text-muted);
  font-size: var(--font-size-sm);
}

.package-price {
  display: flex;
  justify-content: center;
  align-items: baseline;
  gap: var(--space-xs);
  margin-bottom: var(--space-xs);
}

.package-price .price-value {
  font-size: var(--font-size-3xl);
}

.savings {
  font-size: var(--font-size-sm);
  color: var(--color-secondary);
  font-weight: var(--font-weight-semibold);
}

.package-btn {
  width: 100%;
  background: var(--color-secondary);
  color: var(--text-inverse);
  border: none;
  padding: var(--space-md);
  border-radius: var(--radius-md);
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-base);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
  transition: var(--transition-normal);
  margin: 0 var(--space-xl) var(--space-xl);
}

.package-btn:hover {
  background: var(--color-secondary-dark);
  transform: translateY(-2px);
}

/* Info Section */
.pricing-info-section {
  margin-top: var(--space-2xl);
}

.info-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--space-lg);
}

.info-card {
  background: var(--bg-accent);
  padding: var(--space-xl);
  border-radius: var(--radius-lg);
  text-align: center;
  border: 1px solid var(--color-primary);
  transition: var(--transition-fast);
}

.info-card:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.info-icon {
  display: flex;
  justify-content: center;
  color: var(--color-secondary);
  margin-bottom: var(--space-md);
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
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  line-height: var(--line-height-relaxed);
}

/* Responsive Design */
@media (max-width: 1024px) {
  .container {
    padding: 0 var(--space-lg);
  }
  
  .pricing-row {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
    text-align: center;
  }
  
  .service-features {
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .pricing {
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
  
  .table-body {
    padding: var(--space-md);
  }
  
  .pricing-row {
    padding: var(--space-md);
  }
  
  .packages-grid {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
  }
  
  .package-card.featured {
    transform: none;
  }
  
  .package-card.featured:hover {
    transform: translateY(-4px);
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
  
  .section-title {
    font-size: var(--font-size-2xl);
  }
  
  .service-features {
    flex-direction: column;
    align-items: center;
  }
  
  .info-cards {
    grid-template-columns: 1fr;
  }
}

/* Animations */
@media (prefers-reduced-motion: no-preference) {
  .pricing-row,
  .package-card {
    animation: fadeInUp 0.6s ease-out forwards;
    opacity: 0;
  }
}

/* Focus states for accessibility */
.book-btn:focus,
.package-btn:focus {
  outline: 3px solid var(--color-primary);
  outline-offset: 2px;
}
</style>