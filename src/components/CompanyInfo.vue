<script setup>
import { useTranslations } from '../stores/translations'

const { t } = useTranslations()
</script>

<template>
  <section class="section">
    <div class="section-content">
      <h2 class="section-title animate-on-scroll">{{ t('Seven Dates: Здоровый Итальянский Напиток') }}</h2>
      <p class="section-subtitle animate-on-scroll">
        {{ t('Скоро в странах СНГ благодаря сотрудничеству итальянской компании "VitalyV" и "Metamed" в Ташкенте') }}
      </p>

      <div class="section-highlight animate-on-scroll">
        <div class="company-story">
          <div class="story-block animate-on-scroll">
            <h3>{{ t('О Продукте') }}</h3>
            <p>{{ t('Seven Dates - итальянский напиток, который произвел революцию в мире здоровых продуктов с момента его запуска в 2015 году. Продукт характеризуется тем, что он:') }}</p>
            <ul>
              <li>{{ t('100% натуральный') }}</li>
              <li>{{ t('Без добавок') }}</li>
              <li>{{ t('Без сахара') }}</li>
              <li>{{ t('Без искусственных красителей') }}</li>
              <li>{{ t('Производится в Италии') }}</li>
              <li>{{ t('Упаковывается в Европе по официальной лицензии') }}</li>
              <li>{{ t('Соответствует высочайшим международным стандартам качества') }}</li>
              <li>{{ t('Упаковка без БФА и пластика') }}</li>
            </ul>
          </div>

          <div class="quote-block animate-on-scroll">
            <blockquote>
              "{{ t('Наконец-то продукт, который на 100% отражает наши руководящие принципы, продукт для нас и наших детей. Мы призываем граждан читать состав перед употреблением любого продукта и проверять вред, который искусственные ингредиенты, красители и т.д. могут нанести нашему организму.') }}"
              <cite>- Dr. George Muller Mulle</cite>
            </blockquote>
          </div>

          <div class="quote-block animate-on-scroll">
            <blockquote>
              "{{ t('В мире, перенасыщенном подслащенными газированными напитками и искусственно улучшенными напитками, "Seven Dates" предлагает освежающую и революционная альтернатива. Мы создали напиток, который не только вкусный, но и действительно полезный.') }}"
              <cite>- George El Badaoui</cite>
            </blockquote>
          </div>

          <div class="collaboration-block animate-on-scroll">
            <h3>{{ t('О Сотрудничестве') }}</h3>
            <p>{{ t('Сотрудничество между итальянской "VitalyV" и "Metamed" отражает приверженность обеих компаний к предоставлению высококачественных и здоровых продуктов потребителям в регионе. "Metamed", лидер на рынке дистрибуции здоровых продуктов в СНГ с более чем 25-летним опытом, является идеальным партнером для представления революционного напитка "Seven Dates" потребителям в регионе.') }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section {
  position: relative;
  width: 100%;
  overflow-x: hidden;
  padding: var(--space-xl) 0;
}

.section-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-md);
  position: relative;
  z-index: 2;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-md);
  overflow: hidden;
}

.section-highlight {
  width: 100%;
  max-width: 100%;
  margin: var(--space-xl) 0;
  padding: var(--space-lg);
  position: relative;
  overflow: hidden;
}

.company-story {
  display: flex;
  flex-direction: column;
  gap: var(--space-lg);
  width: 100%;
  max-width: 100%;
}

.story-block {
  width: 100%;
  max-width: 100%;
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  box-shadow: var(--shadow-md);
  transition: all 0.3s ease;
  overflow: hidden;
}

.story-block:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-lg);
}

.story-block h3 {
  color: rgb(25, 62, 29);
  margin-bottom: var(--space-md);
  font-size: 1.8rem;
}

.story-block p {
  color: rgb(25, 62, 29);
  line-height: 1.6;
  margin-bottom: var(--space-md);
}

.story-block ul {
  list-style: none;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--space-md);
}

.story-block li {
  position: relative;
  padding-left: 1.5rem;
  color: rgb(25, 62, 29);
}

.story-block li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: rgb(25, 62, 29);
  font-weight: bold;
}

.quote-block {
  background: rgba(25, 62, 29, 0.05);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  border-left: 4px solid rgb(25, 62, 29);
}

.quote-block blockquote {
  margin: 0;
  color: rgb(25, 62, 29);
  font-style: italic;
  line-height: 1.6;
}

.quote-block cite {
  display: block;
  margin-top: var(--space-md);
  color: rgb(25, 62, 29);
  font-weight: 600;
}

.collaboration-block {
  background: rgba(25, 62, 29, 0.05);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
}

.collaboration-block h3 {
  color: rgb(25, 62, 29);
  margin-bottom: var(--space-md);
  font-size: 1.8rem;
}

.collaboration-block p {
  color: rgb(25, 62, 29);
  line-height: 1.6;
}

@media (max-width: 768px) {
  .section {
    padding: var(--space-lg) 0;
  }

  .section-content {
    padding: 0 var(--space-sm);
  }

  .section-highlight {
    padding: var(--space-md);
    margin: var(--space-lg) 0;
  }

  .story-block ul {
    grid-template-columns: 1fr;
  }
}
</style> 