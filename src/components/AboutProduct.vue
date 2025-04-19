<template>
  <section id="about" class="about-section">
    <div class="container">
      <h2 class="section-title animate-on-scroll">
        О продукте
      </h2>
      
      <div class="about-content">
        <div class="product-image animate-on-scroll">
          <img src="../assets/img1.png" alt="Seven Dates Classic" class="product-img">
        </div>
        
        <div class="product-info animate-on-scroll">
          <h3 class="product-title">Seven Dates Classic</h3>
          <p class="product-description">
            Натуральный финиковый напиток премиум-класса, созданный в Италии. 
            Исключительно из отборных фиников, без добавления сахара, консервантов и искусственных красителей.
          </p>
          
          <div class="product-features">
            <div class="feature-item">
              <span class="feature-icon">🌿</span>
              <span class="feature-text">100% натуральный состав</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">🚫</span>
              <span class="feature-text">Без сахара и консервантов</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">🏭</span>
              <span class="feature-text">Производство в Италии</span>
            </div>
            <div class="feature-item">
              <span class="feature-icon">🌍</span>
              <span class="feature-text">Международные стандарты качества</span>
            </div>
          </div>
          
          <div class="product-benefits">
            <h4>Польза для здоровья:</h4>
            <ul>
              <li>Богат натуральными витаминами и минералами</li>
              <li>Поддерживает энергетический баланс</li>
              <li>Улучшает пищеварение</li>
              <li>Содержит антиоксиданты</li>
              <li>Подходит для вегетарианцев</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 6rem 0;
  background: var(--color-background);
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
  color: var(--color-primary);
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
}

.product-img {
  max-width: 100%;
  height: auto;
  object-fit: contain;
  transform: rotate(-15deg);
  filter: drop-shadow(0 20px 30px rgba(0, 0, 0, 0.4));
  transition: transform 0.3s ease;
}

.product-image:hover .product-img {
  transform: rotate(-10deg) scale(1.05);
}

.product-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.product-title {
  font-size: 2rem;
  color: var(--color-primary);
  font-family: var(--font-secondary);
  margin-bottom: 1rem;
}

.product-description {
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--color-text);
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
  border: 1px solid rgba(46, 74, 47, 0.1);
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
  color: var(--color-text);
  font-weight: 500;
}

.product-benefits {
  background: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: var(--radius-lg);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(46, 74, 47, 0.1);
}

.product-benefits h4 {
  font-size: 1.3rem;
  color: var(--color-primary);
  margin-bottom: 1.5rem;
  font-family: var(--font-secondary);
}

.product-benefits ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.product-benefits li {
  position: relative;
  padding-left: 2rem;
  color: var(--color-text);
  line-height: 1.6;
}

.product-benefits li::before {
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
}
</style> 