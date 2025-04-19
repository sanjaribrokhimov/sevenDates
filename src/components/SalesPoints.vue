<template>
  <section id="sales" class="sales-section">
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
        <span class="title-accent">Точки продажи</span>
      </h2>
      
      <div class="sales-content">
        <div class="map-container animate-on-scroll" :class="{ 'animate-in': isIntersecting }">
          <div class="map-placeholder">
            <!-- Здесь будет встроена карта -->
            <div class="map-overlay">
              <p>Карта точек продажи Seven Dates</p>
            </div>
          </div>
        </div>

        <div class="locations-grid">
          <div 
            v-for="(location, index) in locations" 
            :key="index"
            class="location-card animate-on-scroll"
            :class="{ 'animate-in': isIntersecting }"
            :style="{ '--delay': index * 0.2 + 's' }"
          >
            <div class="location-image">
              <img :src="location.image" :alt="location.name">
            </div>
            <div class="location-info">
              <h3>{{ location.name }}</h3>
              <p class="address">{{ location.address }}</p>
              <p class="hours">{{ location.hours }}</p>
              <a :href="location.mapLink" target="_blank" class="map-link">
                <span class="map-icon">📍</span>
                Открыть на карте
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isIntersecting = ref(false)

const locations = [
  {
    name: 'Торговый центр "Самарканд Дарвоза"',
    address: 'г. Ташкент, ул. Самарканд Дарвоза, 1',
    hours: 'Ежедневно с 9:00 до 22:00',
    image: '../assets/location1.jpg',
    mapLink: 'https://maps.google.com/?q=41.3111,69.2797'
  },
  {
    name: 'Супермаркет "Makro"',
    address: 'г. Ташкент, ул. Мирзо Улугбека, 45',
    hours: 'Ежедневно с 8:00 до 23:00',
    image: '../assets/location2.jpg',
    mapLink: 'https://maps.google.com/?q=41.3153,69.2812'
  },
  {
    name: 'Торговый центр "Next"',
    address: 'г. Ташкент, ул. Амира Темура, 107',
    hours: 'Ежедневно с 10:00 до 22:00',
    image: '../assets/location3.jpg',
    mapLink: 'https://maps.google.com/?q=41.3127,69.2801'
  },
  {
    name: 'Супермаркет "Korzinka"',
    address: 'г. Ташкент, ул. Шота Руставели, 12',
    hours: 'Ежедневно с 8:00 до 23:00',
    image: '../assets/location4.jpg',
    mapLink: 'https://maps.google.com/?q=41.3145,69.2789'
  },
  {
    name: 'Торговый центр "Parus"',
    address: 'г. Ташкент, ул. Амира Темура, 88',
    hours: 'Ежедневно с 10:00 до 22:00',
    image: '../assets/location5.jpg',
    mapLink: 'https://maps.google.com/?q=41.3132,69.2795'
  },
  {
    name: 'Супермаркет "Carrefour"',
    address: 'г. Ташкент, ул. Буюк Ипак Йули, 56',
    hours: 'Ежедневно с 8:00 до 23:00',
    image: '../assets/location6.jpg',
    mapLink: 'https://maps.google.com/?q=41.3167,69.2823'
  }
]

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

<style scoped>
.sales-section {
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

.sales-content {
  display: grid;
  gap: 4rem;
}

.map-container {
  opacity: 0;
  transform: translateY(50px);
  transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
}

.map-container.animate-in {
  opacity: 1;
  transform: translateY(0);
}

.map-placeholder {
  width: 100%;
  height: 500px;
  background: var(--color-primary);
  border-radius: 20px;
  overflow: hidden;
  position: relative;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.map-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.3);
  color: white;
  font-size: 1.5rem;
  font-family: var(--font-logo);
}

.locations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.location-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  overflow: hidden;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  opacity: 0;
  transform: translateY(30px);
  animation: slideUp 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-delay: var(--delay);
}

.location-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.location-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.location-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.location-card:hover .location-image img {
  transform: scale(1.1);
}

.location-info {
  padding: 2rem;
  color: var(--color-primary);
}

.location-info h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  font-family: var(--font-logo);
}

.address {
  margin-bottom: 0.5rem;
  opacity: 0.9;
}

.hours {
  margin-bottom: 1.5rem;
  opacity: 0.8;
}

.map-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--color-primary);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.map-link:hover {
  color: var(--color-gold);
  transform: translateX(5px);
}

.map-icon {
  font-size: 1.2rem;
}

@keyframes patternMove {
  0% { background-position: 0 0; }
  100% { background-position: 100px 100px; }
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
  .title-accent {
    font-size: 3rem;
  }

  .map-placeholder {
    height: 300px;
  }

  .locations-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .title-accent {
    font-size: 2.5rem;
  }

  .location-info h3 {
    font-size: 1.3rem;
  }
}
</style> 