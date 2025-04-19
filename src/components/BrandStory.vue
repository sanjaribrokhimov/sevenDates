<script setup>
import { ref } from 'vue'

const storySections = ref([
  {
    title: 'О продукте',
    content: 'Seven Dates Original — натуральный слабо газированный напиток на основе фиников, созданный в Италии и упакованный в Европе. Он отражает философию "чистый состав — настоящий вкус — без компромиссов".',
    image: '/assets/story1.jpg',
    features: [
      '100% натуральный состав',
      'Концентрат лучших фиников',
      'Натуральный лимонный сок',
      'Газированная вода',
      'Без сахара, консервантов, красителей и кофеина',
      'Без аллергенов',
      'Только натуральные экстракты'
    ]
  },
  {
    title: 'Преимущества',
    content: 'Seven Dates — это больше, чем просто напиток. Это стиль жизни, выбор осознанного потребителя и продукт, который объединяет качество, натуральность и европейские стандарты.',
    image: '/assets/story2.jpg',
    features: [
      'Альтернатива сладкой газировке',
      'Подходит для ЗОЖ-питания',
      'Соответствует халяль-стандартам',
      'Подходит для веганов и детей',
      'Современный минималистичный дизайн',
      'Премиум-качество и эко-философия'
    ]
  },
  {
    title: 'О компании',
    content: 'METAMED — официальный представитель и дистрибьютор Seven Dates в СНГ, партнёр итальянской компании VitalyV. 25-летний опыт в логистике и дистрибуции позволяет нам обеспечить надежное сопровождение, бесперебойные поставки и развитие бренда на локальных рынках.',
    image: '/assets/story3.jpg',
    contact: {
      address: 'г.Ташкент, Сергелийский район, ул. Олтин Водий 3-тупик, 111',
      instagram: '@seven_dates.uz',
      email: 'info@metamed.uz',
      phone: '+998 97 757-44-88'
    }
  }
])
</script>

<template>
  <section class="brand-story">
    <div class="container">
      <h2 class="section-title animate-on-scroll">О Seven Dates</h2>
      <div class="story-grid">
        <div v-for="(section, index) in storySections" 
             :key="index" 
             class="story-card animate-on-scroll">
          <div class="story-content">
            <h3 class="story-title">{{ section.title }}</h3>
            <p class="story-text">{{ section.content }}</p>
            
            <div v-if="section.features" class="features-list">
              <div v-for="(feature, idx) in section.features" 
                   :key="idx" 
                   class="feature-item">
                <span class="feature-icon">✓</span>
                <span class="feature-text">{{ feature }}</span>
              </div>
            </div>

            <div v-if="section.contact" class="contact-info">
              <div class="contact-item">
                <span class="contact-icon">📍</span>
                <span>{{ section.contact.address }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">🌐</span>
                <span>{{ section.contact.instagram }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">📧</span>
                <span>{{ section.contact.email }}</span>
              </div>
              <div class="contact-item">
                <span class="contact-icon">📲</span>
                <span>{{ section.contact.phone }}</span>
              </div>
            </div>
          </div>
          <div class="story-image">
            <img :src="section.image" :alt="section.title" class="story-img">
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
  padding: var(--space-lg);
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
  color: var(--color-primary);
  margin-bottom: var(--space-md);
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 1.5px;
}

.story-text {
  color: var(--color-primary);
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

.story-image {
  order: 1;
  border-radius: var(--radius-md);
  overflow: hidden;
}

.story-img {
  width: 100%;
  height: auto;
  object-fit: cover;
  border-radius: var(--radius-md);
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