<template>
  <section class="about" id="about">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <h2 class="section-title cyrillic-text">Обо мне</h2>
        <p class="section-subtitle cyrillic-text">
          Позвольте рассказать о моем пути в мире целительного массажа
        </p>
      </div>

      <!-- Main Content -->
      <div class="about-content">
        <!-- Professional Bio -->
        <div class="bio-section">
          <div class="therapist-photo">
            <div class="photo-placeholder">
              <div class="photo-icon">
                <svg width="80" height="80" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <circle cx="12" cy="8" r="4" stroke="currentColor" stroke-width="2"/>
                  <path d="M6 21v-2a4 4 0 0 1 4-4h4a4 4 0 0 1 4 4v2" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <span class="cyrillic-text">Раца Лилия</span>
            </div>
          </div>
          
          <div class="bio-content">
            <h3 class="therapist-name cyrillic-text">Раца Лилия</h3>
            <p class="therapist-title cyrillic-text">Сертифицированный массажный терапевт</p>
            
            <div class="bio-text">
              <p class="cyrillic-text">
                Привет! Меня зовут Лилия, и вот уже 15 лет я помогаю людям обрести гармонию 
                тела и души через искусство массажа. Мой путь начался с желания помочь близким, 
                а превратился в призвание всей жизни.
              </p>
              <p class="cyrillic-text">
                Я работаю в уютном кабинете у себя дома, где создана особая атмосфера спокойствия 
                и доверия. Каждый мой клиент получает не просто массаж, а персональную заботу 
                и внимание к своим уникальным потребностям.
              </p>
              <p class="cyrillic-text">
                Для меня массаж — это диалог рук с телом, где каждое движение направлено 
                на восстановление внутреннего баланса и освобождение от напряжения.
              </p>
            </div>
          </div>
        </div>

        <!-- Qualifications & Certifications -->
        <div class="qualifications-section">
          <h3 class="qualifications-title cyrillic-text">Моя квалификация</h3>
          
          <div class="qualifications-grid">
            <div class="qualification-card">
              <div class="qualification-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M12 6.042A8.967 8.967 0 0 0 6 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 0 1 6 18c2.305 0 4.408.867 6 2.292A8.987 8.987 0 0 1 18 18a8.967 8.967 0 0 1 3 .512V4.262c-.938-.332-1.948-.512-3-.512A8.967 8.967 0 0 0 12 6.042Z" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Высшее образование</h4>
              <p class="cyrillic-text">Медицинский университет, специализация "Физиотерапия и реабилитация"</p>
            </div>

            <div class="qualification-card">
              <div class="qualification-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Лицензия</h4>
              <p class="cyrillic-text">Государственная лицензия на осуществление медицинской деятельности</p>
            </div>

            <div class="qualification-card">
              <div class="qualification-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M19 14l-7 7m0 0l-7-7m7 7V3" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Сертификаты</h4>
              <p class="cyrillic-text">Специализированные курсы по шведскому, тайскому и лечебному массажу</p>
            </div>

            <div class="qualification-card">
              <div class="qualification-icon">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M12 14l9-5-9-5-9 5 9 5z" stroke="currentColor" stroke-width="2"/>
                  <path d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <h4 class="cyrillic-text">Повышение квалификации</h4>
              <p class="cyrillic-text">Регулярное обучение новым техникам и методам массажной терапии</p>
            </div>
          </div>
        </div>

        <!-- Experience & Philosophy -->
        <div class="philosophy-section">
          <div class="philosophy-content">
            <h3 class="philosophy-title cyrillic-text">Моя философия</h3>
            <div class="philosophy-text">
              <p class="cyrillic-text">
                Для меня массаж — это не просто техника, а способ общения с телом на языке прикосновений. 
                Я слушаю ваше тело и отвечаю именно тем, что ему нужно в данный момент. 
                Каждый сеанс — это уникальная история исцеления.
              </p>
            </div>
            
            <div class="stats-container">
              <div class="stat-item">
                <span class="stat-number">15+</span>
                <span class="stat-label cyrillic-text">лет опыта</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">300+</span>
                <span class="stat-label cyrillic-text">благодарных клиентов</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">8</span>
                <span class="stat-label cyrillic-text">техник массажа</span>
              </div>
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
.about {
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

/* Main Content */
.about-content {
  display: flex;
  flex-direction: column;
  gap: var(--space-3xl);
}

/* Bio Section */
.bio-section {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: var(--space-2xl);
  align-items: start;
}

.therapist-photo {
  position: sticky;
  top: var(--space-xl);
}

.photo-placeholder {
  background: var(--bg-accent);
  border: 2px solid var(--color-primary);
  border-radius: var(--radius-xl);
  height: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: var(--space-md);
  color: var(--color-secondary);
  transition: var(--transition-normal);
}

.photo-placeholder:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-lg);
}

.photo-icon svg {
  color: var(--color-secondary);
  opacity: 0.7;
}

.photo-placeholder span {
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);
  color: var(--text-muted);
}

.bio-content {
  padding-top: var(--space-md);
}

.therapist-name {
  font-size: var(--font-size-3xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.therapist-title {
  font-size: var(--font-size-lg);
  font-family: 'Open Sans', sans-serif;
  font-weight: var(--font-weight-medium);
  color: var(--color-secondary);
  margin-bottom: var(--space-xl);
}

.bio-text p {
  font-size: var(--font-size-base);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-secondary);
  margin-bottom: var(--space-lg);
}

/* Qualifications Section */
.qualifications-section {
  background: var(--bg-secondary);
  padding: var(--space-2xl);
  border-radius: var(--radius-xl);
  border: 1px solid var(--color-gray-200);
}

.qualifications-title {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  text-align: center;
  margin-bottom: var(--space-xl);
}

.qualifications-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-lg);
}

.qualification-card {
  background: var(--bg-primary);
  padding: var(--space-xl);
  border-radius: var(--radius-lg);
  text-align: center;
  border: 1px solid var(--color-gray-200);
  transition: var(--transition-normal);
}

.qualification-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-lg);
  border-color: var(--color-primary);
}

.qualification-icon {
  display: flex;
  justify-content: center;
  margin-bottom: var(--space-md);
  color: var(--color-secondary);
}

.qualification-card h4 {
  font-size: var(--font-size-lg);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.qualification-card p {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-secondary);
}

/* Philosophy Section */
.philosophy-section {
  text-align: center;
}

.philosophy-title {
  font-size: var(--font-size-2xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--space-lg);
}

.philosophy-text {
  max-width: 800px;
  margin: 0 auto var(--space-2xl);
}

.philosophy-text p {
  font-size: var(--font-size-lg);
  font-family: 'Open Sans', sans-serif;
  line-height: var(--line-height-relaxed);
  color: var(--text-secondary);
  font-style: italic;
}

/* Stats Container */
.stats-container {
  display: flex;
  justify-content: center;
  gap: var(--space-2xl);
  flex-wrap: wrap;
}

.stat-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: var(--space-lg);
  background: var(--bg-accent);
  border-radius: var(--radius-lg);
  border: 1px solid var(--color-primary);
  min-width: 120px;
  transition: var(--transition-fast);
}

.stat-item:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.stat-number {
  font-size: var(--font-size-3xl);
  font-family: 'Montserrat', sans-serif;
  font-weight: var(--font-weight-bold);
  color: var(--color-secondary);
  line-height: 1;
}

.stat-label {
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  font-weight: var(--font-weight-medium);
  color: var(--text-secondary);
  margin-top: var(--space-xs);
  text-align: center;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .container {
    padding: 0 var(--space-lg);
  }
  
  .bio-section {
    grid-template-columns: 250px 1fr;
    gap: var(--space-xl);
  }
  
  .stats-container {
    gap: var(--space-lg);
  }
}

@media (max-width: 768px) {
  .about {
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
  
  .bio-section {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
    text-align: center;
  }
  
  .therapist-photo {
    position: static;
  }
  
  .photo-placeholder {
    height: 250px;
    max-width: 250px;
    margin: 0 auto;
  }
  
  .therapist-name {
    font-size: var(--font-size-2xl);
  }
  
  .qualifications-section {
    padding: var(--space-xl);
  }
  
  .qualifications-grid {
    grid-template-columns: 1fr;
    gap: var(--space-md);
  }
  
  .qualification-card {
    padding: var(--space-lg);
  }
  
  .stats-container {
    flex-direction: column;
    align-items: center;
    gap: var(--space-md);
  }
  
  .stat-item {
    min-width: 100px;
    padding: var(--space-md);
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
  
  .section-title {
    font-size: var(--font-size-2xl);
  }
  
  .about-content {
    gap: var(--space-2xl);
  }
  
  .photo-placeholder {
    height: 200px;
    max-width: 200px;
  }
  
  .therapist-name {
    font-size: var(--font-size-xl);
  }
  
  .philosophy-text p {
    font-size: var(--font-size-base);
  }
}

/* Animation for scroll-triggered elements */
@media (prefers-reduced-motion: no-preference) {
  .qualification-card,
  .stat-item {
    animation: fadeInUp 0.6s ease-out forwards;
  }
  
  .qualification-card:nth-child(2) {
    animation-delay: 0.1s;
  }
  
  .qualification-card:nth-child(3) {
    animation-delay: 0.2s;
  }
  
  .qualification-card:nth-child(4) {
    animation-delay: 0.3s;
  }
}
</style>