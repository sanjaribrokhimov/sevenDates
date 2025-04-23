<script setup>
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()
</script>

<template>
  <section id="specs" class="specs-section">
    <div class="container">
      <h2 class="section-title">{{ t('Технические характеристики') }}</h2>
      <div class="specs-content">
        <div class="specs-grid">
          <div class="specs-card">
            <div class="icon">📦</div>
            <h3>{{ t('Упаковка') }}</h3>
            <ul class="specs-list">
              <li>• {{ t('Объём') }}: 250 мл</li>
              <li>• {{ t('Материал') }}: {{ t('Алюминий') }}</li>
              <li>• {{ t('Без БФА') }}</li>
              <li>• {{ t('Срок годности') }}: 24 {{ t('месяца') }}</li>
            </ul>
          </div>

          <div class="specs-card">
            <div class="icon">🌱</div>
            <h3>{{ t('Состав') }}</h3>
            <ul class="specs-list">
              <li>• {{ t('Финиковый концентрат') }}</li>
              <li>• {{ t('Очищенная вода') }}</li>
              <li>• {{ t('Натуральные экстракты') }}</li>
              <li>• {{ t('Без консервантов') }}</li>
            </ul>
          </div>

          <div class="specs-card">
            <div class="icon">📊</div>
            <h3>{{ t('Пищевая ценность') }}<br>{{ t('на 100мл') }}</h3>
            <ul class="specs-list">
              <li>• {{ t('Энергетическая ценность') }}: 45 {{ t('ккал') }}</li>
              <li>• {{ t('Белки') }}: 0.5 {{ t('г') }}</li>
              <li>• {{ t('Жиры') }}: 0 {{ t('г') }}</li>
              <li>• {{ t('Углеводы') }}: 11 {{ t('г') }}</li>
            </ul>
          </div>

          <div class="specs-card">
            <div class="icon">🏆</div>
            <h3>{{ t('Сертификация') }}</h3>
            <ul class="specs-list">
              <li>• ISO 9001:2015</li>
              <li>• HACCP</li>
              <li>• Halal</li>
              <li>• FDA Registered</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.specs-section {
  padding: 6rem 0;
  background: rgb(250, 247, 237);
  position: relative;
  overflow: hidden;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 4rem;
  color: rgb(209, 190, 156);
  font-family: var(--font-secondary);
}

.specs-content {
  max-width: 1200px;
  margin: 0 auto;
}

.specs-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}

.specs-card {
  background: white;
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  text-align: left;
}

.icon {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.specs-card h3 {
  font-size: 1.3rem;
  color: rgb(25, 62, 29);
  margin-bottom: 1.5rem;
  font-weight: 600;
  line-height: 1.4;
}

.specs-list {
  list-style: none;
  padding: 0;
  margin: 0;
  color: rgb(25, 62, 29);
}

.specs-list li {
  margin-bottom: 0.75rem;
  font-size: 1rem;
  line-height: 1.5;
}

.specs-list li:last-child {
  margin-bottom: 0;
}

@media (max-width: 1024px) {
  .specs-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .specs-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 3rem;
  }
}

@media (max-width: 480px) {
  .specs-grid {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 1.8rem;
  }

  .specs-card {
    padding: 1.5rem;
  }
}
</style> 