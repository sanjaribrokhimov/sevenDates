<script setup>
import { ref } from 'vue'
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()

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
  <section id="specs" class="specs-section">
    <div class="container">
      <h2 class="section-title animate-on-scroll">
        {{ t('Технические характеристики') }}
      </h2>
      
      <div class="specs-grid">
        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">📦</div>
          <div class="spec-content">
            <h3>{{ t('Упаковка') }}</h3>
            <ul class="spec-list">
              <li>• {{ t('Объём') }}: 250 мл</li>
              <li>• {{ t('Материал') }}: {{ t('Алюминий') }} ({{ t('Без БФА') }})</li>
              <li>• {{ t('Срок годности') }}: 14 {{ t('месяца') }}</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">🌱</div>
          <div class="spec-content">
            <h3>{{ t('Состав') }}</h3>
            <ul class="spec-list">
              <li>• {{ t('Очищенная вода') }}</li>
              <li>• {{ t('Финиковый концентрат') }}</li>
              <li>• {{ t('Натуральный лимонный сок') }}</li>
              <li>• {{ t('Газированная вода') }}</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">📊</div>
          <div class="spec-content">
            <h3>{{ t('Пищевая ценность') }}<br>{{ t('на 100мл') }}</h3>
            <ul class="spec-list">
              <li>• {{ t('Энергетическая ценность') }}: 45 {{ t('ккал') }}</li>
              <li>• {{ t('Белки') }}: 0.5 {{ t('г') }}</li>
              <li>• {{ t('Жиры') }}: 0 {{ t('г') }}</li>
              <li>• {{ t('Углеводы') }}: 11 {{ t('г') }}</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">🏆</div>
          <div class="spec-content">
            <h3>{{ t('Сертификация') }}</h3>
            <ul class="spec-list">
              <li>• {{ t('ISO 9001:2015') }}</li>
              <li>• {{ t('HACCP') }}</li>
              <li>• Halal</li>
              <li>• FDA Registered</li>
            </ul>
          </div>
        </div>

        <div class="specs-image-container animate-on-scroll">
          <img src="../assets/img2.png" alt="" class="specs-image">
         
          <img src="../assets/img3.png" alt="" class="specs-image">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.specs-section {
  padding: 6rem 0;
  color: var(--color-primary);
  position: relative;
  overflow: hidden;
}

.specs-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  opacity: 0.1;
}

.container {
  max-width: 1400px;  /* Увеличил максимальную ширину для размещения 4 блоков */
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 1;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 4rem;
  color: var(--color-primary);
  font-family: var(--font-secondary);
}

.specs-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.spec-card {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(46, 74, 47, 0.1);
}

.spec-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.spec-icon {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
}

.spec-content {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.spec-content h3 {
  margin-bottom: 1rem;
}

.spec-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.spec-list li {
  margin-bottom: 0.8rem;
  padding-left: 1.5rem;
  position: relative;
  color: var(--color-text);
}

.spec-list li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@media (max-width: 1200px) {
  .specs-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .specs-image-container {
    grid-column: 1 / span 2;
    grid-row: auto;
    flex-direction: row;
    justify-content: center;
    gap: 2rem;
  }

  .specs-image {
    width: 40%;
    height: 250px;
  }

  .image-overlay {
    width: 40%;
    top: 10%;
  }
}

@media (max-width: 768px) {
  .specs-section {
    padding: 3rem 1rem;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 2rem;
    text-align: center;
  }

  .specs-grid {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
    padding: 0;
  }
  
  .spec-card {
    padding: 2rem;
    width: 100%;
    max-width: 400px;
    margin: 0;
    background: white;
    border-radius: 20px;
  }

  .spec-icon {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    text-align: center;
  }

  .spec-content {
    text-align: center;
  }

  .spec-content h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--color-primary);
  }

  .spec-list {
    text-align: left;
    padding-left: 1rem;
  }

  .spec-list li {
    margin-bottom: 0.5rem;
    font-size: 1rem;
  }

  .specs-image-container {
    width: 100%;
    max-width: 400px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
    margin: 1rem 0;
  }

  .specs-image {
    width: 100%;
    height: 280px;
    object-fit: contain;
    background: white;
    border-radius: 20px;
    padding: 1rem;
  }

  .image-overlay {
    width: 100%;
    top: 10%;
  }

  .overlay-text {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .specs-section {
    padding: 2rem 1rem;
  }

  .section-title {
    font-size: 1.8rem;
  }

  .spec-card {
    padding: 1.5rem;
  }

  .spec-content h3 {
    font-size: 1.3rem;
  }

  .specs-image {
    height: 240px;
  }

  .overlay-text {
    font-size: 1.8rem;
  }
}

.specs-image-container {
  grid-column: 3 / span 2;
  grid-row: 1 / span 2;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 2rem;
  position: relative;
}

.specs-image {
  width: 100%;
  height: 40%;
  object-fit: cover;
  margin: 0 auto;
}

.image-overlay {
  position: absolute;
  top: 5%;
  left: 0;
  width: 50%;
  text-align: center;
  z-index: 2;
}

.overlay-text {
  font-family: var(--font-secondary);
  font-size: 2.5rem;
  color: #2E4A2F;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
}
</style> 