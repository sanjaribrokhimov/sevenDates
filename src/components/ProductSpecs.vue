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
  <section id="specs" class="specs-section">
    <div class="container">
      <h2 class="section-title animate-on-scroll">
        Технические характеристики
      </h2>

      <div class="specs-grid">
        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">📦</div>
          <div class="spec-content">
            <h3>Упаковка</h3>
            <ul class="spec-list">
              <li>Объем: 250 мл</li>
              <li>Материал: Алюминий</li>
              <li>Без БФА</li>
              <li>Срок годности: 24 месяца</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">🌱</div>
          <div class="spec-content">
            <h3>Состав</h3>
            <ul class="spec-list">
              <li>Финиковый концентрат</li>
              <li>Очищенная вода</li>
              <li>Натуральные экстракты</li>
              <li>Без консервантов</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">📊</div>
          <div class="spec-content">
            <h3>Пищевая ценность на 100мл</h3>
            <ul class="spec-list">
              <li>Энергетическая ценность: 45 ккал</li>
              <li>Белки: 0.5 г</li>
              <li>Жиры: 0 г</li>
              <li>Углеводы: 11 г</li>
            </ul>
          </div>
        </div>

        <div class="spec-card animate-on-scroll">
          <div class="spec-icon">🏆</div>
          <div class="spec-content">
            <h3>Сертификация</h3>
            <ul class="spec-list">
              <li>ISO 9001:2015</li>
              <li>HACCP</li>
              <li>Halal</li>
              <li>FDA Registered</li>
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
  background: #f0f7f0;  /* Очень светлый зеленый фон */
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
  grid-template-columns: repeat(4, 1fr);  /* 4 блока в ряд */
  gap: 2rem;
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
  display: inline-block;
  animation: float 3s ease-in-out infinite;
}

.spec-content h3 {
  font-size: 1.3rem;
  color: var(--color-primary);
  margin-bottom: 1rem;
  font-family: var(--font-secondary);
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
}

@media (max-width: 768px) {
  .specs-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 3rem;
  }

  .specs-grid {
    grid-template-columns: 1fr;
  }

  .spec-card {
    padding: 1.5rem;
  }

  .spec-icon {
    font-size: 2rem;
  }

  .spec-content h3 {
    font-size: 1.2rem;
  }
}
</style> 