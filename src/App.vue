<script setup>
import Navigation from './components/Navigation.vue'
import MediaSection from './components/MediaSection.vue'
import BrandStory from './components/BrandStory.vue'
import Partnership from './components/Partnership.vue'
import ProductSpecs from './components/ProductSpecs.vue'
import ContactSection from './components/ContactSection.vue'
import CompanyInfo from './components/CompanyInfo.vue'
import SalesPoints from './components/SalesPoints.vue'
import { onMounted } from 'vue'

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
        <div class="animated-background">
          <div class="animated-shape shape-line"></div>
          <div class="animated-shape shape-circle"></div>
          <div class="animated-shape shape-hexagon"></div>
          <div class="animated-shape shape-line"></div>
        </div>

        <div class="hero-container">
          <div class="hero-content">
            <div class="logo-container animate-on-scroll">
              <h1 class="main-title">
                <span class="text-gradient">Seven Dates</span>
              </h1>
            </div>
            <p class="hero-description animate-on-scroll">
              Натуральный финиковый напиток из Италии
            </p>
            <div style="color: gold;" class="hero-features animate-on-scroll">
              <span class="feature hover-scale">Без красителей</span>
              <br>
              <span class="feature hover-scale">Без консервантов</span>
              <br>
              <span class="feature hover-scale">100% натуральный</span>
            </div>
            <a href="#about" class="btn learn-more animate-on-scroll">
              Узнать больше
              <span class="btn-arrow">→</span>
            </a>
          </div>
          <div class="hero-image animate-on-scroll">
            <img src=".//assets/img1.png" alt="Seven Dates Classic" class="can-image">
          </div>
        </div>
      </section>

      <MediaSection />
      <SalesPoints />
      <AboutProduct />
      <CompanyInfo />
      <BrandStory />
      <ProductSpecs />
      <Partnership />
      <Benefits />
      <ContactSection />
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
  padding: 0;
  margin: 0;
  background: linear-gradient(135deg, 
    rgba(25, 40, 26, 0.95) 0%,
    rgba(46, 74, 47, 0.9) 100%
  );
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
}

@media (max-width: 768px) {
  .hero-container {
    grid-template-columns: 1fr;
    padding: 2rem;
    gap: var(--space-xl);
  }

  .hero-content {
    text-align: center;
  }

  .hero-image {
    justify-content: center;
  }

  .can-image {
    max-height: 60vh;
  }
}

.logo-container {
  animation: fadeInLeft 1s ease-out forwards;
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.main-title {
  font-size: 8rem;
  line-height: 1;
  margin-bottom: var(--space-sm);
  position: relative;
  text-shadow: 0 0 20px rgba(255, 215, 0, 0.3),
               0 0 40px rgba(255, 215, 0, 0.2);
  background: linear-gradient(135deg, 
    #FFE08A 0%,
    #FFD700 50%,
    #FFB900 100%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 4px rgba(255, 215, 0, 0.5));
}

.main-title::after {
  content: '';
  position: absolute;
  top: -10px;
  left: -20px;
  right: -20px;
  bottom: -10px;
  
  z-index: -1;
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
  color:white;
  margin-bottom: var(--space-lg);
  opacity: 0.9;
}

.learn-more {
  font-size: 1.1rem;
  padding: 1rem 2.5rem;
  background: var(--gradient-primary);
}

.btn-arrow {
  display: inline-block;
  margin-left: 0.5rem;
  transition: transform 0.3s ease;
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

@media (max-width: 768px) {
  .hero-container {
    grid-template-columns: 1fr;
    gap: var(--space-xl);
  }

  .hero-content {
    text-align: center;
    order: 2;
    margin-top: 0;
  }

  .hero-image {
    order: 1;
    justify-content: center;
    margin-top: 0;
    transform: translateY(0);
  }

  .main-title {
    font-size: 4rem;
  }

  .classic-text {
    font-size: 2.5rem;
  }

  .hero-description {
    font-size: 1.2rem;
  }

  .hero-features {
    justify-content: center;
  }

  .feature {
    padding: 0.5rem 1rem;
  }
}

@media (max-width: 480px) {
  .main-title {
    font-size: 3rem;
  }

  .classic-text {
    font-size: 2rem;
  }

  .hero-description {
    font-size: 1rem;
  }

  .feature {
    padding: 0.4rem 1rem;
    font-size: 0.9rem;
  }

  .learn-more {
    font-size: 1rem;
    padding: 0.75rem 1.5rem;
  }
}
</style>
