<script setup>
import Navigation from './components/Navigation.vue'
import MediaSection from './components/MediaSection.vue'
import BrandStory from './components/BrandStory.vue'
import Partnership from './components/Partnership.vue'
import ProductSpecs from './components/ProductSpecs.vue'
import ContactSection from './components/ContactSection.vue'
import CompanyInfo from './components/CompanyInfo.vue'
import SalesPoints from './components/SalesPoints.vue'
import AboutProduct from './components/AboutProduct.vue'
import LangSwitcher from './components/LangSwitcher.vue'
import { useTranslations } from './stores/translations'

import { onMounted } from 'vue'

const { t } = useTranslations()

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in')
        observer.unobserve(entry.target)
      }
    })
  }, {
    threshold: 0.1
  })

  document.querySelectorAll('.animate-on-scroll').forEach(el => {
    observer.observe(el)
  })
})
</script>

<template>
  <div class="app-wrapper">
    <Navigation />
    
    <main>
      <section class="hero-section">
        <div class="hero-container">
          <div class="hero-content">
            <div class="logo-container">
              <div class="title-wrapper">
                <h1 class="main-title">
                  <span class="text-gradient">Seven</span>
                  <span class="text-gradient">Dates</span>
                </h1>
              </div>
              <div class="product-type">{{ t('PREMIUM HALAL НАПИТОК') }}</div>
            </div>
            <p class="hero-description animate-on-scroll">
              {{ t('Натуральный финиковый напиток из Италии') }}
              <span class="flag">🇮🇹</span>
            </p>
            <div style="color:black; font-weight: bold;" class="hero-features animate-on-scroll">
              <span class="feature hover-scale">{{ t('Без красителей') }}</span>
              <br>
              <span class="feature hover-scale">{{ t('Без консервантов') }}</span>
              <br>
              <span class="feature hover-scale">{{ t('100% натуральный') }}</span>
            </div>
            <a href="#about" class="btn learn-more animate-on-scroll">
              {{ t('Узнать больше') }}
              <span class="btn-arrow">→</span>
            </a>
          </div>
          <div class="hero-image animate-on-scroll">
            <img src="./assets/img1.png" alt="Seven Dates Classic" class="can-image">
          </div>
        </div>
      </section>

      
      <section id="about">
        <AboutProduct />
      </section>

      <section id="specs">
        <ProductSpecs />
      </section>
      
      <section id="company">
        <CompanyInfo />
      </section>
      
      <section id="story">
        <BrandStory />
      </section>

      <section id="media">
        <MediaSection />
      </section>

      <section id="sales">
        <SalesPoints />
      </section>
      
      <section id="partnership">
        <Partnership />
      </section>
      
      <section id="contacts">
        <ContactSection />
      </section>
    </main>
  </div>
</template>

<style>
.app-wrapper {
  min-height: 100vh;
  width: 100%;
  overflow-x: hidden;
  background-color: rgb(250, 247, 237);
}

.hero-section {
  min-height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding: 6rem 0 0 0;
  margin: 0;
  background: rgb(209, 190, 156);
}

.animated-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  z-index: 1;
}

.animated-shape {
  position: absolute;
  opacity: 0;
  mix-blend-mode: screen;
}

.shape-line {
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, 
    transparent 0%,
    rgba(255, 215, 0, 0.4) 50%,
    transparent 100%
  );
  animation: lineMove 8s infinite;
}

.shape-circle {
  border-radius: 50%;
  background: radial-gradient(circle at center,
    rgba(255, 215, 0, 0.3) 0%,
    rgba(46, 124, 47, 0.2) 50%,
    transparent 100%
  );
  animation: circleFloat 12s infinite;
}

.shape-hexagon {
  width: 200px;
  height: 200px;
  background: linear-gradient(45deg,
    rgba(255, 215, 0, 0.2) 0%,
    rgba(46, 124, 47, 0.15) 100%
  );
  clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
  animation: hexagonSpin 15s infinite;
}

.animated-shape:nth-child(1) {
  top: 20%;
  left: -10%;
  width: 120%;
  animation-delay: 0s;
}

.animated-shape:nth-child(2) {
  top: 40%;
  left: 30%;
  width: 300px;
  height: 300px;
  animation-delay: 2s;
}

.animated-shape:nth-child(3) {
  bottom: 30%;
  right: 20%;
  animation-delay: 4s;
}

.animated-shape:nth-child(4) {
  top: 60%;
  left: -10%;
  width: 120%;
  animation-delay: 1s;
}

@keyframes lineMove {
  0% { transform: translateX(-100%) rotate(-5deg); opacity: 0; }
  20% { opacity: 0.7; }
  80% { opacity: 0.7; }
  100% { transform: translateX(100%) rotate(-5deg); opacity: 0; }
}

@keyframes circleFloat {
  0% { transform: translate(0, 0) scale(0.8); opacity: 0; }
  25% { transform: translate(50px, -30px) scale(1.2); opacity: 0.6; }
  50% { transform: translate(100px, 0) scale(1); opacity: 0.8; }
  75% { transform: translate(50px, 30px) scale(1.1); opacity: 0.6; }
  100% { transform: translate(0, 0) scale(0.8); opacity: 0; }
}

@keyframes hexagonSpin {
  0% { transform: rotate(0deg) scale(0.8); opacity: 0; }
  30% { transform: rotate(120deg) scale(1.2); opacity: 0.6; }
  60% { transform: rotate(240deg) scale(1); opacity: 0.8; }
  100% { transform: rotate(360deg) scale(0.8); opacity: 0; }
}

.hero-container {
  position: relative;
  z-index: 2;
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  padding: 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  align-items: center;
}

.hero-content {
  text-align: left;
  padding: 0;
  position: relative;
  z-index: 2;
}

.hero-image {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  position: relative;
  z-index: 2;
  width: 100%;
  height: 100%;
}

.can-image {
  max-height: 80vh;
  width: auto;
  object-fit: contain;
  transform: rotate(-15deg);
  filter: drop-shadow(0 20px 30px rgba(0, 0, 0, 0.4));
  animation: floatingCan 4s ease-in-out infinite;
}

@keyframes floatingCan {
  0% {
    transform: rotate(-15deg) translateY(0px);
  }
  50% {
    transform: rotate(-8deg) translateY(-25px);
  }
  100% {
    transform: rotate(-15deg) translateY(0px);
  }
}

@media (max-width: 768px) {
  .hero-container {
    grid-template-columns: 1fr;
    padding: 2rem;
    gap: 0;
    text-align: center;
  }

  .hero-content {
    text-align: center;
    order: 2;
    padding-top: 2rem;
  }

  .hero-features {
    display: none;
  }

  .hero-image {
    order: 1;
    justify-content: center;
    margin: 0 auto;
    max-width: 80%;
    margin-top: 3.5rem;
  }

  .can-image {
    max-height: 50vh;
    margin: 0 auto;
    margin-bottom: 1.5rem;
    animation: floatingCanMobile 4s ease-in-out infinite;
  }

  .title-wrapper {
    gap: 1rem;
  }
  
  .dates-img {
    width: 60px;
    height: 60px;
  }
  
  .main-title {
    font-size: 3rem;
    line-height: 1.1;
  }

  .main-title .text-gradient:first-child {
    display: block;
    margin-bottom: 0.2em;
  }

  .main-title .text-gradient:last-child {
    display: block;
  }
}

@keyframes floatingCanMobile {
  0% {
    transform: rotate(-15deg) translateY(0px);
  }
  50% {
    transform: rotate(-10deg) translateY(-20px);
  }
  100% {
    transform: rotate(-15deg) translateY(0px);
  }
}

@media (max-width: 480px) {
  .hero-container {
    padding: 1rem;
  }

  .dates-img {
    width: 30px;
    height: 30px;
  }
  
  .main-title {
    font-size: 1.4rem;
  }

  .hero-description {
    font-size: 1.1rem;
  }

  .can-image {
    max-height: 45vh;
  }

  .hero-features {
    font-size: 0.9rem;
  }
}

.logo-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 2rem;
  position: relative;
}

.title-wrapper {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 1rem;
}

.dates-img {
  width: 90px;
  height: 90px;
  object-fit: contain;
}

.main-title {
  font-size: 6rem;
  line-height: 1;
  margin: 0;
  position: relative;
  color: rgb(25, 62, 29);
  text-shadow: 2px 2px 4px rgba(25, 62, 29, 0.2);
  white-space: nowrap;
}

.classic-text {
  font-size: 5.5rem;
  font-family: var(--font-secondary);
  margin-top: var(--space-sm);
  animation: glowText 3s ease-in-out infinite;
  background: linear-gradient(135deg, #FFE08A 0%, #FFD700 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 4px rgba(255, 215, 0, 0.3));
}

.hero-description {
  font-size: 1.5rem;
  color: rgb(25, 62, 29);
  margin-bottom: var(--space-lg);
  opacity: 0.9;
}

.learn-more {
  font-size: 1.1rem;
  padding: 1rem 2.5rem;
  background: rgb(25, 62, 29);
  color: white;
  border-radius: 30px;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  box-shadow: 0 4px 15px rgba(25, 62, 29, 0.2);
  font-weight: 600;
  letter-spacing: 0.5px;
  margin-top: 2rem;
}

.learn-more:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 20px rgba(25, 62, 29, 0.3);
  background: rgb(35, 82, 39);
}

.btn-arrow {
  display: inline-block;
  margin-left: 0.5rem;
  transition: transform 0.3s ease;
  color: white;
}

.btn:hover .btn-arrow {
  transform: translateX(5px);
}

@keyframes glowText {
  0%, 100% {
    filter: drop-shadow(0 2px 4px rgba(255, 215, 0, 0.3));
  }
  50% {
    filter: drop-shadow(0 4px 8px rgba(255, 215, 0, 0.5));
  }
}

.product-type {
  font-family: var(--font-secondary);
  font-size: 1.2rem;
  color: rgb(25, 62, 29);
  margin-top: 0.5rem;
  letter-spacing: 2px;
  text-align: center;
}

.flag {
  font-size: 1.2em;
  vertical-align: middle;
  margin-left: 0.5rem;
}

.navigation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 1rem 0;
  transition: all 0.3s ease;
  background: rgb(209, 190, 156);
  box-shadow: var(--shadow-lg);
  border-bottom: 1px solid rgba(25, 62, 29, 0.1);
}

.nav-link {
  color: rgb(25, 62, 29);
  font-weight: 600;
  font-size: 1rem;
  padding: 0.5rem 1rem;
  transition: all 0.3s ease;
}

.nav-link:hover {
  opacity: 0.8;
  transform: translateY(-2px);
}

.logo {
  color: rgb(25, 62, 29);
  font-weight: bold;
  font-size: 1.5rem;
}

.media-section {
  position: relative;
  overflow: hidden;
  padding: 8rem 2rem;
  background: rgb(239, 205, 158);
}

.section-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgb(239, 205, 158);
  z-index: -1;
}

.nav-contact-info {
  color: rgb(25, 62, 29);
}

.nav-contact-link {
  color: rgb(25, 62, 29) !important;
}

.nav-social-link {
  color: rgb(25, 62, 29) !important;
  background: rgba(25, 62, 29, 0.1);
}

.nav-social-link:hover {
  background: rgba(25, 62, 29, 0.2);
}
</style>
