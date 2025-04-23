<script setup>
import { ref } from 'vue'
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()
</script>

<template>
  <section class="brand-story">
    <div class="container">
      <h2 style="color: rgb(25, 62, 29);" class="section-title animate-on-scroll">{{ t('Преимущества Seven Dates') }}</h2>
      <div class="story-grid">
        <div class="story-card animate-on-scroll">
          <div class="story-content">
            <h3 class="story-title">{{ t('Продукт') }}</h3>
            <p class="story-text">{{ t('Seven Dates Original — натуральный слабо газированный напиток на основе фиников, созданный в Италии и упакованный в Европе. Он отражает философию "чистый состав — настоящий вкус — без компромиссов".') }}</p>
            
            <div class="features-list">
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Концентрат лучших фиников') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Натуральный лимонный сок') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Газированная вода') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Без сахара, консервантов, красителей и кофеина') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Без аллергенов') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Только натуральные экстракты') }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="story-card animate-on-scroll">
          <div class="story-content">
            <h3 class="story-title">{{ t('Преимущества') }}</h3>
            <p class="story-text">{{ t('Seven Dates — это больше, чем просто напиток. Это стиль жизни, выбор осознанного потребителя и продукт, который объединяет качество, натуральность и европейские стандарты.') }}</p>
            
            <div class="features-list">
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Альтернатива сладкой газировке') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Подходит для ЗОЖ-питания') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Соответствует халяль-стандартам') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Подходит для веганов и детей') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Современный минималистичный дизайн') }}</span>
              </div>
              <div class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ t('Премиум-качество и эко-философия') }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="story-card animate-on-scroll">
          <div class="story-content">
            <h3 class="story-title">{{ t('Компания') }}</h3>
            <p class="story-text">{{ t('METAMED — официальный представитель и дистрибьютор Seven Dates в СНГ, партнёр итальянской компании VitalyV. 25-летний опыт в логистике и дистрибуции позволяет нам обеспечить надежное сопровождение, бесперебойные поставки и развитие бренда на локальных рынках.') }}</p>
            
            <div class="contact-info">
              <div class="contact-item">
                <span class="contact-icon">-</span>
                <span>{{ t('г.Ташкент, Сергелийский район, ул. Олтин Водий 3-тупик, 111') }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">-</span>
                <span>{{ t('@seven_dates.uz') }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">-</span>
                <span>{{ t('info@metamed.uz') }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">-</span>
                <span>{{ t('+998 97 757-44-88') }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">-</span>
                <span>{{ t('+998 97 757-44-88') }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.brand-story {
  width: 100%;
  overflow-x: hidden;
  padding: var(--space-xl) 0;
  background: rgb(250, 247, 237);
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-md);
  overflow: hidden;
}

.section-title {
  text-align: center;
  font-size: 3.5rem;
  margin-bottom: var(--space-xl);
  color: var(--color-primary);
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 2px;
}

.story-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--space-lg);
  width: 100%;
  margin: 0 auto;
}

.story-card {
  width: 100%;
  background: rgba(255, 255, 255, 0.9);
  border-radius: var(--radius-lg);
  padding: 30px;
  box-shadow: var(--shadow-md);
  transition: all 0.3s ease;
}

.story-card:hover {
  transform: translateY(-5px);
}

.story-content {
  width: 100%;
  overflow: hidden;
}

.story-title {
  font-size: 2.2rem;
  margin-bottom: var(--space-md);
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 1.5px;
}

.story-text {
  opacity: 0.9;
  line-height: 1.6;
  margin-bottom: var(--space-md);
  font-family: var(--font-primary);
  font-size: 1.1rem;
}

.features-list {
  margin-top: var(--space-md);
}

.feature-item {
  display: flex;
  align-items: center;
  gap: var(--space-sm);
  margin-bottom: var(--space-sm);
  color: var(--color-text-light);
}

.feature-icon {
  color: #4CAF50;
  font-weight: bold;
}

.contact-info {
  margin-top: var(--space-lg);
  display: flex;
  flex-direction: column;
  gap: var(--space-sm);
}

.contact-item {
  display: flex;
  align-items: center;
  gap: var(--space-sm);
  color: var(--color-text-light);
}

.contact-icon {
  font-size: 1.2em;
}

@media (max-width: 1200px) {
  .story-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .story-grid {
    grid-template-columns: 1fr;
  }
  
  .container {
    padding: 0 var(--space-sm);
  }
  
  .story-card {
    padding: var(--space-md);
  }
}
</style> 