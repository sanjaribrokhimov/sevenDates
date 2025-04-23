<script setup>
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()
</script>

<template>
  <section id="partnership" class="partnership-section">
    <div class="container">
      <h2 class="section-title animate-on-scroll">{{ t('Сотрудничество') }}</h2>
      
      <div class="partnership-grid">
        <div class="partnership-card animate-on-scroll">
          <div class="card-icon">🤝</div>
          <h3>{{ t('Дистрибьюторам') }}</h3>
          <p>{{ t('Станьте официальным дистрибьютором Seven Dates в вашем регионе. Мы предлагаем выгодные условия сотрудничества и полную поддержку бизнеса.') }}</p>
          <ul class="benefits-list">
            <li>{{ t('Эксклюзивные права на территорию') }}</li>
            <li>{{ t('Маркетинговая поддержка') }}</li>
            <li>{{ t('Обучение персонала') }}</li>
            <li>{{ t('Рекламные материалы') }}</li>
          </ul>
        </div>

        <div class="partnership-card animate-on-scroll">
          <div class="card-icon">🏪</div>
          <h3>{{ t('Розничным сетям') }}</h3>
          <p>{{ t('Расширьте ассортимент вашего магазина премиальным натуральным напитком. Привлекайте новую аудиторию и увеличивайте продажи.') }}</p>
          <ul class="benefits-list">
            <li>{{ t('Гибкие условия поставок') }}</li>
            <li>{{ t('Поддержка продаж') }}</li>
            <li>{{ t('POS-материалы') }}</li>
            <li>{{ t('Программы лояльности') }}</li>
          </ul>
        </div>

        <div class="partnership-card animate-on-scroll">
          <div class="card-icon">🍽️</div>
          <h3>{{ t('Ресторанны') }}</h3>
          <p>{{ t('Добавьте в свое меню уникальный безалкогольный напиток. Идеально подходит для ресторанов, кафе, отелей и кейтеринговых компаний.') }}</p>
          <ul class="benefits-list">
            <li>{{ t('Специальные условия') }}</li>
            <li>{{ t('Обучение персонала') }}</li>
            <li>{{ t('Брендированные материалы') }}</li>
            <li>{{ t('Техническая поддержка') }}</li>
          </ul>
        </div>
      </div>

      <div class="contact-block animate-on-scroll">
        <h3>{{ t('Свяжитесь с нами') }}</h3>
        <div class="contact-info">
          <a href="tel:+998977574488" class="contact-link">
            <span class="icon">📞</span>
            +998 97 757 44 88
          </a>
          <a href="mailto:partner@sevendates.uz" class="contact-link">
            <span class="icon">✉️</span>
            partner@sevendates.uz
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.partnership-section {
  padding: 6rem 0;
  background: var(--gradient-section);
  position: relative;
  overflow: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 4rem;
  font-family: var(--font-secondary);
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 3px;
  background: var(--gradient-gold);
  border-radius: 2px;
}

.partnership-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.partnership-card {
  background: white;
  border-radius: 20px;
  padding: 2.5rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  overflow: hidden;
}

.partnership-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: var(--gradient-gold);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.partnership-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.partnership-card:hover::before {
  opacity: 1;
}

.card-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
  display: inline-block;
  animation: float 3s ease-in-out infinite;
}

.partnership-card h3 {
  font-size: 1.5rem;
  color: var(--color-primary);
  margin-bottom: 1rem;
  font-family: var(--font-secondary);
}

.partnership-card p {
  color: var(--color-text);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.benefits-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.benefits-list li {
  margin-bottom: 0.8rem;
  padding-left: 1.5rem;
  position: relative;
  color: var(--color-text);
}

.benefits-list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: bold;
}

.contact-block {
  text-align: center;
  background: rgb(25, 62, 29);
  border-radius: 20px;
  padding: 3rem;
  color: white;
  margin-top: 4rem;
}

.contact-block h3 {
  font-size: 1.8rem;
  margin-bottom: 2rem;
  color: white;
  font-family: var(--font-secondary);
}

.contact-info {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.contact-link {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  color: white;
  text-decoration: none;
  font-size: 1.2rem;
  padding: 1rem 2rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50px;
  transition: all 0.3s ease;
}

.contact-link:hover {
  background: var(--color-secondary);
  transform: translateY(-3px);
}

.icon {
  font-size: 1.4rem;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@media (max-width: 768px) {
  .partnership-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 3rem;
  }

  .partnership-card {
    padding: 2rem;
  }

  .card-icon {
    font-size: 2.5rem;
  }

  .partnership-card h3 {
    font-size: 1.3rem;
  }

  .contact-block {
    padding: 2rem;
  }

  .contact-block h3 {
    font-size: 1.5rem;
  }

  .contact-link {
    width: 100%;
    justify-content: center;
  }
}
</style> 