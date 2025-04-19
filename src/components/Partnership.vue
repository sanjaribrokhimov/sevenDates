<script setup>
import { ref } from 'vue'

const partnershipInfo = ref({
  title: 'Сотрудничество',
  description: 'Станьте частью перспективного и быстрорастущего направления — здоровых альтернатив привычным сладким напиткам.',
  benefits: [
    {
      title: 'Высокая маржинальность',
      items: [
        'Высокий спрос на рынке',
        'Гибкие условия сотрудничества',
        'Возможность эксклюзива по региону'
      ]
    },
    {
      title: 'Поддержка продаж',
      items: [
        'Рекламные материалы',
        'Дегустации',
        'Презентации'
      ]
    },
    {
      title: 'Условия поставки',
      items: [
        'Выкуп / отсрочка',
        'Минимальная партия — от 1 паллеты (3744 шт по 250 мл)',
        'Бесперебойные поставки'
      ]
    }
  ],
  salesChannels: [
    'Супермаркеты и ритейл',
    'Аптеки и эко-магазины',
    'Фитнес-клубы',
    'Кафе и кофейни'
  ]
})
</script>

<template>
  <section class="partnership">
    <div class="container">
      <h2 class="section-title animate-on-scroll">{{ partnershipInfo.title }}</h2>
      <p class="description animate-on-scroll">{{ partnershipInfo.description }}</p>
      
      <div class="benefits-grid">
        <div v-for="(benefit, index) in partnershipInfo.benefits" 
             :key="index" 
             class="benefit-card animate-on-scroll">
          <h3 class="benefit-title">{{ benefit.title }}</h3>
          <ul class="benefit-list">
            <li v-for="(item, idx) in benefit.items" 
                :key="idx" 
                class="benefit-item">
              <span class="check-icon">✓</span>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>

      <div class="sales-channels animate-on-scroll">
        <h3 class="channels-title">Каналы сбыта</h3>
        <div class="channels-grid">
          <div v-for="(channel, index) in partnershipInfo.salesChannels" 
               :key="index" 
               class="channel-item">
            <span class="channel-icon">🏪</span>
            <span class="channel-text">{{ channel }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.partnership {
  padding: var(--space-xl) 0;
  background: rgb(250, 247, 237);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-lg);
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

.description {
  text-align: center;
  font-size: 1.2rem;
  color: var(--color-primary);
  margin-bottom: var(--space-xl);
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  font-family: var(--font-primary);
}

.benefits-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-lg);
  margin-bottom: var(--space-xl);
}

.benefit-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  backdrop-filter: blur(10px);
  transition: transform 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-5px);
}

.benefit-title {
  font-size: 2rem;
  color: var(--color-primary);
  margin-bottom: var(--space-md);
  text-align: center;
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 1.5px;
}

.benefit-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: var(--space-sm);
  color: var(--color-text-light);
  margin-bottom: var(--space-sm);
  font-size: 1.1rem;
}

.check-icon {
  color: #4CAF50;
  font-weight: bold;
}

.sales-channels {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  backdrop-filter: blur(10px);
}

.channels-title {
  text-align: center;
  font-size: 2.2rem;
  color: var(--color-primary);
  margin-bottom: var(--space-lg);
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 1.5px;
}

.channels-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--space-md);
}

.channel-item {
  display: flex;
  align-items: center;
  gap: var(--space-sm);
  color: var(--color-text-light);
  font-size: 1.1rem;
}

.channel-icon {
  font-size: 1.5rem;
}

@media (min-width: 768px) {
  .benefits-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .channels-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (min-width: 1024px) {
  .benefits-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style> 