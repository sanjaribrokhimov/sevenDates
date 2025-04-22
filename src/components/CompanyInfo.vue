<template>
  <section class="section">
    <div class="section-content">
      <h2 class="section-title animate-on-scroll">Seven Dates: Здоровый Итальянский Напиток</h2>
      <p class="section-subtitle animate-on-scroll">
        Скоро в странах СНГ благодаря сотрудничеству итальянской компании "VitalyV" и "Metamed" в Ташкенте
      </p>

      <div class="section-highlight animate-on-scroll">
        <div class="company-story">
          <div class="story-block animate-on-scroll">
            <h3>О Продукте</h3>
            <p>Seven Dates - итальянский напиток, который произвел революцию в мире здоровых продуктов с момента его запуска в 2015 году. Продукт характеризуется тем, что он:</p>
            <ul>
              <li>100% натуральный</li>
              <li>Без добавок</li>
              <li>Без сахара</li>
              <li>Без искусственных красителей</li>
              <li>Производится в Италии</li>
              <li>Упаковывается в Европе по официальной лицензии</li>
              <li>Соответствует высочайшим международным стандартам качества</li>
              <li>Упаковка без БФА и пластика</li>
            </ul>
          </div>

          <div class="quote-block animate-on-scroll">
            <blockquote>
              "Наконец-то продукт, который на 100% отражает наши руководящие принципы, продукт для нас и наших детей. Мы призываем граждан читать состав перед употреблением любого продукта и проверять вред, который искусственные ингредиенты, красители и т.д. могут нанести нашему организму."
              <cite>- Dr. George Muller Mulle</cite>
            </blockquote>
          </div>

          <div class="quote-block animate-on-scroll">
            <blockquote>
              "В мире, перенасыщенном подслащенными газированными напитками и искусственно улучшенными напитками, 'Seven Dates' предлагает освежающую и революционную альтернативу. Мы создали напиток, который не только вкусный, но и действительно полезный."
              <cite>- George El Badaoui</cite>
            </blockquote>
          </div>

          <div class="story-block animate-on-scroll">
            <h3>Наши Преимущества</h3>
            <ul>
              <li>100% натуральный состав</li>
              <li>Без рафинированных сахаров</li>
              <li>Без фосфорной и лимонной кислот</li>
              <li>Без искусственных консервантов</li>
              <li>Без красителей</li>
              <li>Без БФА в банках</li>
              <li>Без добавленного кофеина</li>
              <li>Без аллергенов</li>
            </ul>
          </div>

          <div class="collaboration-block animate-on-scroll">
            <h3>О Сотрудничестве</h3>
            <p>Сотрудничество между итальянской "VitalyV" и "Metamed" отражает приверженность обеих компаний к предоставлению высококачественных и здоровых продуктов потребителям в регионе. "Metamed", лидер на рынке дистрибуции здоровых продуктов в СНГ с более чем 25-летним опытом, является идеальным партнером для представления революционного напитка "Seven Dates" потребителям в регионе.</p>
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
  margin-bottom: var(--space-md);
  line-height: 1.8;
  color: var(--color-text);
}

.story-block ul {
  list-style: none;
  padding: 0;
}

.story-block ul li {
  position: relative;
  padding-left: 2rem;
  margin-bottom: 0.8rem;
  line-height: 1.6;
}

.story-block ul li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-secondary);
  font-weight: bold;
}

.quote-block {
  background: linear-gradient(135deg, rgb(25, 62, 29) 0%, #1E2F1F 100%);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  color: var(--color-white);
  position: relative;
  overflow: hidden;
}

.quote-block::before {
  content: '"';
  position: absolute;
  top: -20px;
  left: 20px;
  font-size: 8rem;
  font-family: var(--font-secondary);
  color: rgba(255, 255, 255, 0.1);
}

blockquote {
  font-size: 1.2rem;
  line-height: 1.8;
  margin: 0;
  position: relative;
  z-index: 1;
}

cite {
  display: block;
  margin-top: var(--space-sm);
  font-size: 1rem;
  color: var(--color-secondary);
  font-style: normal;
}

.collaboration-block {
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  box-shadow: var(--shadow-md);
}

@media (max-width: 768px) {
  .section-content,
  .container,
  .section-highlight,
  .story-block {
    padding: var(--space-md);
  }

  .story-block h3 {
    font-size: 1.5rem;
  }

  blockquote {
    font-size: 1.1rem;
  }

  .story-block ul li {
    font-size: 0.95rem;
  }
}
</style> 