<template>
  <section class="packages" id="packages">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <h2 class="section-title cyrillic-text">Пакетные предложения</h2>
        <p class="section-subtitle cyrillic-text">
          Экономьте больше с курсами массажа для глубокого оздоровления
        </p>
      </div>

      <!-- Packages Grid -->
      <div class="packages-grid">
        <div 
          class="package-card" 
          v-for="(pkg, index) in packages" 
          :key="pkg.id"
          :style="{ animationDelay: `${index * 0.2}s` }"
        >
          <!-- Package Icon -->
          <div class="package-icon" v-html="pkg.icon"></div>
          
          <!-- Package Content -->
          <div class="package-content">
            <h3 class="package-name cyrillic-text">{{ pkg.name }}</h3>
            <p class="package-description cyrillic-text">{{ pkg.description }}</p>
            
            <!-- Package Features -->
            <ul class="package-features">
              <li v-for="feature in pkg.features" :key="feature" class="cyrillic-text">
                {{ feature }}
              </li>
            </ul>
            
            <!-- Package Details -->
            <div class="package-details">
              <div class="sessions cyrillic-text">
                <span class="sessions-label">Количество сеансов:</span>
                <span class="sessions-value">{{ pkg.sessions }}</span>
              </div>
              <div class="savings cyrillic-text">
                <span class="savings-label">Экономия:</span>
                <span class="savings-value">{{ pkg.savings }}</span>
              </div>
            </div>

            <!-- Price -->
            <div class="package-price">
              <div class="price-original cyrillic-text">
                <span class="original-label">Обычная цена:</span>
                <span class="original-value">{{ pkg.originalPrice }} руб.</span>
              </div>
              <div class="price-package">
                <span class="package-price-value">{{ pkg.packagePrice }}</span>
                <span class="package-price-currency cyrillic-text">руб.</span>
              </div>
            </div>
          </div>
          
          <!-- Book Button -->
          <button class="book-package-button cyrillic-text" @click="bookPackage">
            Записаться на курс
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Package Icons as SVG strings
const icons = {
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

const packages = ref([
  {
    id: 1,
    name: 'Недельный курс',
    description: 'Интенсивная программа восстановления. Три сеанса массажа на выбор в течение недели для максимального эффекта.',
    features: ['Любые 3 вида массажа на выбор', 'Гибкий график записи', 'Персональные рекомендации', 'Скидка 15%'],
    sessions: '3 сеанса',
    savings: '15%',
    originalPrice: '10500',
    packagePrice: '8925',
    icon: icons.weeklyPackage
  },
  {
    id: 2,
    name: 'Месячный курс',
    description: 'Полная программа оздоровления и релаксации. Восемь сеансов различных техник массажа в течение месяца.',
    features: ['Любые 8 видов массажа', 'Индивидуальная программа', 'Консультации между сеансами', 'Скидка 25%'],
    sessions: '8 сеансов',
    savings: '25%',
    originalPrice: '28000',
    packagePrice: '21000',
    icon: icons.monthlyPackage
  }
])

const bookPackage = () => {
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
.packages {
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

/* Packages Grid */
.packages-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--space-2xl);
  margin-bottom: var(--space-2xl);
}

/* Package Card */
.package-card {
  background: var(--bg-secondary);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-lg);
  border: 2px solid var(--color-primary);
  overflow: hidden;
  transition: var(--transition-normal);
  display: flex;
  flex-direction: column;
  position: relative;
}

.package-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 6px;
  background: linear-gradient(90deg, var(--color-secondary), var(--color-primary));
}

.package-card:hover {
  transform: translateY(-12px) scale(1.03);
  box-shadow: 0 25px 50px rgba(107, 142, 35, 0.2);
  border-color: var(--color-secondary);
  background: linear-gradient(135deg, var(--bg-secondary), rgba(210, 180, 140, 0.08));
}

.package-card:hover .package-price {
  background: linear-gradient(135deg, var(--color-primary), rgba(210, 180, 140, 0.3));
  transform: scale(1.02);
}

/* Package Icon */
.package-icon {
  padding: var(--space-2xl) var(--space-xl) var(--space-lg);
  display: flex;
  justify-content: center;
  color: var(--color-secondary);
  transition: var(--transition-normal);
}

.package-card:hover .package-icon {
  color: var(--color-secondary-dark);
  transform: scale(1.15);
}

/* Package Content */
.package-content {
  padding: 0 var(--space-xl);
  flex: 1;
  display: flex;
  flex-direction: column;
}

.package-name {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  margin-bottom: var(--space-md);
  text-align: center;
}

.package-description {
  font-size: var(--font-size-base);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-secondary);
  margin-bottom: var(--space-lg);
  text-align: center;
}

/* Package Features */
.package-features {
  list-style: none;
  padding: 0;
  margin: 0 0 var(--space-lg) 0;
  flex: 1;
}

.package-features li {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
  padding: var(--space-sm) 0;
  position: relative;
  padding-left: var(--space-lg);
}

.package-features li::before {
  content: '★';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: var(--font-weight-bold);
}

/* Package Details */
.package-details {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-md);
  padding: var(--space-md);
  background: var(--bg-accent);
  border-radius: var(--radius-lg);
  margin-bottom: var(--space-lg);
}

.sessions, .savings {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.sessions-label, .savings-label {
  font-size: var(--font-size-xs);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: var(--space-xs);
}

.sessions-value, .savings-value {
  font-size: var(--font-size-base);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
}

/* Package Price */
.package-price {
  background: var(--color-primary);
  padding: var(--space-lg);
  border-radius: var(--radius-lg);
  margin-bottom: var(--space-lg);
  text-align: center;
  transition: var(--transition-normal);
}

.price-original {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: var(--space-sm);
  margin-bottom: var(--space-sm);
}

.original-label {
  font-size: var(--font-size-xs);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-muted);
  text-transform: uppercase;
}

.original-value {
  font-size: var(--font-size-sm);
  font-family: 'Montserrat', sans-serif;
  color: var(--text-muted);
  text-decoration: line-through;
}

.price-package {
  display: flex;
  align-items: baseline;
  justify-content: center;
  gap: var(--space-xs);
}

.package-price-value {
  font-size: var(--font-size-4xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--color-secondary);
}

.package-price-currency {
  font-size: var(--font-size-lg);
  font-family: 'Open Sans', sans-serif;
  color: var(--text-secondary);
}

/* Book Package Button */
.book-package-button {
  background: var(--color-secondary);
  color: var(--text-inverse);
  border: none;
  padding: var(--space-lg) var(--space-xl);
  margin: 0 var(--space-xl) var(--space-xl);
  border-radius: var(--radius-lg);
  font-family: 'Montserrat', sans-serif;
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
  transition: var(--transition-normal);
  position: relative;
  overflow: hidden;
}

.book-package-button::before {
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

.book-package-button:hover::before {
  left: 100%;
}

.book-package-button:hover {
  background: var(--color-secondary-dark);
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.book-package-button:active {
  transform: translateY(0);
}

/* Responsive Design */
@media (max-width: 1024px) {
  .container {
    padding: 0 var(--space-lg);
  }
  
  .packages-grid {
    gap: var(--space-xl);
  }
}

@media (max-width: 768px) {
  .packages {
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
  
  .packages-grid {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
  }
  
  .package-details {
    grid-template-columns: 1fr;
    gap: var(--space-sm);
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
  
  .section-title {
    font-size: var(--font-size-2xl);
  }
  
  .package-icon {
    padding: var(--space-xl) var(--space-lg) var(--space-md);
  }
  
  .package-content {
    padding: 0 var(--space-lg);
  }
  
  .package-name {
    font-size: var(--font-size-xl);
  }
  
  .package-price-value {
    font-size: var(--font-size-3xl);
  }
  
  .book-package-button {
    margin: 0 var(--space-lg) var(--space-lg);
    padding: var(--space-md) var(--space-lg);
    font-size: var(--font-size-base);
  }
}

/* Animations */
@media (prefers-reduced-motion: no-preference) {
  .package-card {
    animation: fadeInUp 0.8s ease-out forwards;
    opacity: 0;
  }
  
  .package-card:nth-child(1) { animation-delay: 0s; }
  .package-card:nth-child(2) { animation-delay: 0.2s; }
}

/* Focus states for accessibility */
.book-package-button:focus {
  outline: 3px solid var(--color-primary);
  outline-offset: 2px;
}
</style>