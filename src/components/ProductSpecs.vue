<script setup>
import { ref } from 'vue'

const productSpecs = ref({
  title: 'Технические характеристики',
  description: 'Seven Dates Original — натуральный напиток премиум-класса, созданный с учетом всех современных стандартов качества.',
  specifications: [
    {
      category: 'Упаковка',
      items: [
        { label: 'Объём', value: '250 мл' },
        { label: 'Материал', value: 'Алюминий (без бисфенола-А)' },
        { label: 'Срок годности', value: '14 месяцев' }
      ]
    },
    {
      category: 'Состав',
      items: [
        { label: 'Основной ингредиент', value: 'Концентрат фиников' },
        { label: 'Дополнительные компоненты', value: 'Натуральный лимонный сок, газированная вода' },
        { label: 'Без', value: 'Сахар, консерванты, красители, кофеин, аллергены' }
      ]
    },
    {
      category: 'Сертификация',
      items: [
        { label: 'Стандарты', value: 'ЕС, ЕАС' },
        { label: 'Дополнительно', value: 'Халяль' },
        { label: 'Производство', value: 'Италия' }
      ]
    }
  ]
})
</script>

<template>
  <section class="product-specs">
    <div class="container">
      <h2 class="section-title animate-on-scroll">{{ productSpecs.title }}</h2>
      <p class="description animate-on-scroll">{{ productSpecs.description }}</p>
      
      <div class="specs-grid">
        <div v-for="(spec, index) in productSpecs.specifications" 
             :key="index" 
             class="spec-card animate-on-scroll">
          <h3 class="spec-title">{{ spec.category }}</h3>
          <div class="spec-items">
            <div v-for="(item, idx) in spec.items" 
                 :key="idx" 
                 class="spec-item">
              <span class="spec-label">{{ item.label }}</span>
              <span class="spec-value">{{ item.value }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.product-specs {
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
  color: var(--color-text-light);
  margin-bottom: var(--space-xl);
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.specs-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-lg);
}

.spec-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  backdrop-filter: blur(10px);
  transition: transform 0.3s ease;
}

.spec-card:hover {
  transform: translateY(-5px);
}

.spec-title {
  font-size: 2rem;
  color: var(--color-primary);
  margin-bottom: var(--space-md);
  text-align: center;
  font-family: var(--font-secondary);
  font-weight: 400;
  letter-spacing: 1.5px;
  border-bottom: 2px solid rgba(0, 0, 0, 0.1);
  padding-bottom: var(--space-sm);
}

.spec-items {
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
}

.spec-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--space-sm) 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.spec-label {
  color: var(--color-primary);
  opacity: 0.8;
  font-size: 1.1rem;
  font-family: var(--font-secondary);
  letter-spacing: 1px;
}

.spec-value {
  color: var(--color-primary);
  font-weight: 500;
  text-align: right;
  font-family: var(--font-primary);
}

@media (min-width: 768px) {
  .specs-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .specs-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style> 