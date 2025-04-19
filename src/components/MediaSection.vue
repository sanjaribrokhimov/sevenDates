<script setup>
import { ref, onMounted } from 'vue'
import canImage from '../assets/can-image.png'

const selectedImage = ref(null)
const isModalOpen = ref(false)
const isVideoPlaying = ref(false)
const isIntersecting = ref(false)
const videoPlayer = ref(null)

const galleryImages = [
  { 
    src: canImage, 
    alt: 'Seven Dates производство', 
    title: 'Производство в Италии',
    description: 'Современное производство с соблюдением высочайших стандартов качества'
  },
  { 
    src: canImage, 
    alt: 'Seven Dates упаковка', 
    title: 'Современная упаковка',
    description: 'Экологичная упаковка, сохраняющая все полезные свойства напитка'
  },
  { 
    src: canImage, 
    alt: 'Seven Dates ингредиенты', 
    title: 'Натуральные ингредиенты',
    description: 'Только лучшие финики и натуральные компоненты'
  },
  { 
    src: canImage, 
    alt: 'Seven Dates качество', 
    title: 'Контроль качества',
    description: 'Строгий контроль на всех этапах производства'
  },
  { 
    src: canImage, 
    alt: 'Seven Dates команда', 
    title: 'Наша команда',
    description: 'Профессионалы с многолетним опытом в индустрии'
  },
  { 
    src: canImage, 
    alt: 'Seven Dates продукт', 
    title: 'Готовый продукт',
    description: 'Премиальный напиток для ценителей качества'
  }
]

const openModal = (image) => {
  selectedImage.value = image
  isModalOpen.value = true
  document.body.style.overflow = 'hidden'
}

const closeModal = () => {
  isModalOpen.value = false
  document.body.style.overflow = 'auto'
}

const toggleVideo = () => {
  isVideoPlaying.value = !isVideoPlaying.value
  if (isVideoPlaying.value && videoPlayer.value) {
    videoPlayer.value.play()
  } else if (videoPlayer.value) {
    videoPlayer.value.pause()
  }
}

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        isIntersecting.value = true
        observer.unobserve(entry.target)
      }
    })
  }, {
    threshold: 0.1
  })

  const elements = document.querySelectorAll('.animate-on-scroll')
  elements.forEach(el => observer.observe(el))
})
</script>

<template>
  <section id="media" class="media-section">
    <div class="section-background">
      <div class="pattern-overlay"></div>
      <div class="floating-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
      </div>
    </div>
    <div class="container">
      <h2 class="section-title animate-on-scroll" :class="{ 'animate-in': isIntersecting }">
        <span class="title-accent">Seven Dates</span>
      </h2>
      
      <div class="media-content">
        <div class="product-info animate-on-scroll" :class="{ 'animate-in': isIntersecting }">
          <h3 class="product-subtitle">Premium Halal напиток на основе финикового концентрата</h3>
          
          <div class="benefits-grid">
            <div class="benefit-item" v-for="(benefit, index) in benefits" :key="index" :style="{ '--delay': index * 0.2 + 's' }">
              <div class="benefit-icon">{{ benefit.icon }}</div>
              <div class="benefit-content">
                <h4>{{ benefit.title }}</h4>
                <p>{{ benefit.description }}</p>
              </div>
            </div>
          </div>

          <div class="product-features">
            <h4>Содержит:</h4>
            <ul>
              <li>Витамины B-комплекс</li>
              <li>Витамин C</li>
              <li>Магний (Mg)</li>
              <li>Калий (K)</li>
              <li>Кальций (Ca)</li>
              <li>Железо (Fe)</li>
              <li>Антиоксиданты</li>
            </ul>
          </div>

          <div class="product-features">
            <h4>Не содержит:</h4>
            <ul>
              <li>Синтетических добавок</li>
              <li>Консервантов</li>
              <li>Красителей</li>
              <li>Кофеина</li>
              <li>Бисфенола А</li>
              <li>Добавленного сахара</li>
            </ul>
          </div>
        </div>

        <div class="video-container animate-on-scroll" :class="{ 'animate-in': isIntersecting }">
          <div class="video-placeholder hover-scale">
            <video 
              ref="videoPlayer"
              autoplay
              muted
              loop
              playsinline
              class="video-element"
            >
              <source src="../assets/sevendates.mp4" type="video/mp4">
              Ваш браузер не поддерживает видео тег.
            </video>
            <div class="video-overlay">
              <button class="play-button" @click="toggleVideo">
                <span class="play-icon">{{ isVideoPlaying ? '⏸' : '▶' }}</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="modal" v-if="isModalOpen" @click="closeModal">
      <div class="modal-content" @click.stop>
        <button class="modal-close hover-rotate" @click="closeModal">&times;</button>
        <img :src="selectedImage?.src" :alt="selectedImage?.alt" />
        <div class="modal-info">
          <h3 class="text-gradient">{{ selectedImage?.title }}</h3>
          <p>{{ selectedImage?.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.media-section {
  position: relative;
  overflow: hidden;
  padding: 8rem 2rem;
  background: var(--gradient-gold);
}

.section-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: var(--gradient-gold);
  z-index: -1;
}

.pattern-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  opacity: 0.1;
  animation: patternMove 20s linear infinite;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
}

.section-title {
  text-align: center;
  position: relative;
  margin-bottom: 4rem;
  opacity: 0;
  transform: translateY(50px);
  transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
}

.section-title.animate-in {
  opacity: 1;
  transform: translateY(0);
}

.title-accent {
  font-size: 4rem;
  color: var(--color-primary);
  position: relative;
  display: inline-block;
  font-family: var(--font-logo);
  font-weight: 700;
  letter-spacing: 2px;
}

.title-accent::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 3px;
  background: var(--color-primary);
}

.media-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.product-info {
  color: var(--color-primary);
  opacity: 0;
  transform: translateX(-50px);
  transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
}

.product-info.animate-in {
  opacity: 1;
  transform: translateX(0);
}

.product-subtitle {
  font-size: 2rem;
  margin-bottom: 3rem;
  font-family: var(--font-logo);
  font-weight: 600;
  line-height: 1.4;
}

.benefits-grid {
  display: grid;
  gap: 2rem;
  margin-bottom: 3rem;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  opacity: 0;
  transform: translateY(30px);
  animation: slideUp 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-delay: var(--delay);
}

.benefit-icon {
  font-size: 2.5rem;
  min-width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--color-primary);
  color: var(--color-gold);
  border-radius: 50%;
  animation: float 3s ease-in-out infinite;
}

.benefit-content h4 {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  font-family: var(--font-logo);
  color: var(--color-primary);
}

.benefit-content p {
  font-size: 1rem;
  line-height: 1.6;
  color: var(--color-primary);
  opacity: 0.9;
}

.product-features {
  margin-top: 2rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.product-features h4 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  font-family: var(--font-logo);
  color: var(--color-primary);
}

.product-features ul {
  list-style: none;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
}

.product-features li {
  position: relative;
  padding-left: 1.5rem;
  font-size: 1.1rem;
  color: var(--color-primary);
}

.product-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-weight: bold;
}

.video-container {
  text-align: center;
  opacity: 0;
  transform: translateX(50px);
  transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
}

.video-container.animate-in {
  opacity: 1;
  transform: translateX(0);
}

.video-placeholder {
  position: relative;
  border-radius: var(--radius-lg);
  overflow: hidden;
  cursor: pointer;
  margin: 0 auto;
  box-shadow: 
    0 20px 40px rgba(0, 0, 0, 0.2),
    0 0 0 1px rgba(255, 255, 255, 0.1);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  aspect-ratio: 16/9;
  width: 100%;
  max-width: 1000px;
  background: var(--color-primary);
}

.video-element {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.video-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.video-placeholder:hover .video-overlay {
  opacity: 1;
}

.play-button {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--color-primary);
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.play-button:hover {
  transform: scale(1.1);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
}

.play-icon {
  font-size: 2rem;
  color: var(--color-gold);
}

@keyframes patternMove {
  0% { background-position: 0 0; }
  100% { background-position: 100px 100px; }
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@keyframes slideUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.floating-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 0;
}

.shape {
  position: absolute;
  background: var(--color-primary);
  border-radius: 50%;
  opacity: 0.1;
}

.shape-1 {
  width: 300px;
  height: 300px;
  top: -150px;
  left: -150px;
  animation: floatShape 15s ease-in-out infinite;
}

.shape-2 {
  width: 200px;
  height: 200px;
  top: 50%;
  right: -100px;
  animation: floatShape 12s ease-in-out infinite reverse;
}

.shape-3 {
  width: 150px;
  height: 150px;
  bottom: -75px;
  left: 50%;
  animation: floatShape 10s ease-in-out infinite;
}

@keyframes floatShape {
  0% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(30px, 30px) rotate(180deg);
  }
  100% {
    transform: translate(0, 0) rotate(360deg);
  }
}

@media (max-width: 768px) {
  .media-content {
    grid-template-columns: 1fr;
  }

  .title-accent {
    font-size: 3rem;
  }

  .product-subtitle {
    font-size: 1.8rem;
  }

  .product-features ul {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .title-accent {
    font-size: 2.5rem;
  }

  .product-subtitle {
    font-size: 1.5rem;
  }

  .benefit-item {
    flex-direction: column;
    text-align: center;
  }
}
</style> 