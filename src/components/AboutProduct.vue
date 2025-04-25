<script setup>
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()
</script>

<template>
  <section id="about" class="about-section">
    <div class="container">
      <h2 class="section-title">{{ t('О продукте') }}</h2>
      <div class="about-content">
        <div class="product-info">
          <h3 class="product-title">{{ t('Seven Dates ORIGINAL') }}</h3>
          <p class="product-description">
            {{ t('Здоровый финиковый напиток премиум-класса, созданный в Италии. Исключительно из отборных фиников, без добавления сахара, консервантов и искусственных красителей. Полезная альтернатива газированным напиткам.') }}
          </p>
          <div class="product-features">
            <div class="feature-item">
              <span class="feature-icon">🌿</span>
              <span class="feature-text">{{ t('100% натуральный состав') }}</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">💪</span>
              <span class="feature-text">{{ t('Полезный для здоровья') }}</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">📦</span>
              <span class="feature-text">{{ t('Картонная упаковка без пластика') }}</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">⭐</span>
              <span class="feature-text">{{ t('Международные стандарты качества') }}</span>
            </div>
          </div>
          <div class="product-composition">
            <h4>{{ t('Состав:') }}</h4>
            <ul>
              <li>{{ t('Финиковый концентрат') }}</li>
              <li>{{ t('Натуральный лимонный сок') }}</li>
              <li>{{ t('Газированная вода') }}</li>
              <li>{{ t('Натуральные экстракты') }}</li>
            </ul>
          </div>
        </div>
        <div class="product-image">
          <div class="phone-frame">
            <div class="phone-notch"></div>
            <video 
              src="../assets/imgMov.MOV" 
              alt="Seven Dates Original" 
              class="product-img"
              autoplay
              loop
              muted
              playsinline
            >
            </video>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 6rem 0;
  color: black;
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
  color: var(--color-gold);
  font-family: var(--font-secondary);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.product-image {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  perspective: 1000px;
}

.phone-frame {
  position: relative;
  background: linear-gradient(145deg, #0c3e1a, #13390f);
  border-radius: 50px;
  padding: 15px;
  box-shadow: 
    0 20px 40px rgba(0, 0, 0, 0.3),
    0 0 0 2px rgba(255, 215, 0, 0.1);
}

.phone-notch {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 180px;
  height: 30px;
  background: linear-gradient(145deg, #2a2a2a, #1a1a1a);
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 20px;
  z-index: 2;
  box-shadow: 0 -5px 10px rgba(0, 0, 0, 0.2);
}

.product-img {
  max-width: 100%;
  width: 400px;
  height: auto;
  object-fit: cover;
  border-radius: 35px;
}

.product-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.product-title {
  font-size: 2rem;
  color: var(--color-gold);
  font-family: var(--font-secondary);
  margin-bottom: 1rem;
}

.product-description {
  font-size: 1.1rem;
  line-height: 1.8;
  opacity: 0.9;
}

.product-features {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  margin: 2rem 0;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: var(--radius-md);
  backdrop-filter: blur(10px);
  border: 1px solid var(--color-gold);
  transition: all 0.3s ease;
}

.feature-item:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
  background: rgba(255, 255, 255, 0.2);
}

.feature-icon {
  font-size: 1.5rem;
}

.feature-text {
  font-size: 1rem;
  font-weight: 500;
}

.product-composition {
  background: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: var(--radius-lg);
  backdrop-filter: blur(10px);
  border: 1px solid var(--color-gold);
}

.product-composition h4 {
  font-size: 1.3rem;
  margin-bottom: 1.5rem;
  font-family: var(--font-secondary);
}

.product-composition ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.product-composition li {
  position: relative;
  padding-left: 2rem;
  line-height: 1.6;
}

.product-composition li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: bold;
}

@media (max-width: 1200px) {
  .about-content {
    gap: 3rem;
  }
}

@media (max-width: 768px) {
  .about-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 3rem;
  }

  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .product-image {
    order: 2;
  }

  .product-info {
    order: 1;
  }

  .product-title {
    font-size: 1.8rem;
  }

  .product-features {
    grid-template-columns: 1fr;
  }

  .phone-frame {
    padding: 12px;
    border-radius: 40px;
  }

  .phone-notch {
    width: 150px;
    height: 25px;
  }

  .product-img {
    width: 300px;
    border-radius: 30px;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 1.8rem;
  }

  .product-title {
    font-size: 1.5rem;
  }

  .product-description {
    font-size: 1rem;
  }

  .feature-text {
    font-size: 0.9rem;
  }

  .phone-frame {
    padding: 10px;
    border-radius: 35px;
  }

  .phone-notch {
    width: 130px;
    height: 22px;
  }

  .product-img {
    width: 250px;
    border-radius: 25px;
  }
}
</style> 