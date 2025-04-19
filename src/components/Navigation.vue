<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
  document.body.style.overflow = isMobileMenuOpen.value ? 'hidden' : 'auto'
}
</script>

<template>
  <nav class="navigation">
    <div class="nav-container">
      <a href="#" class="logo">
        <span class="text-gradient">SevenDates</span>
      </a>
      
      <button class="mobile-menu-btn" @click="toggleMobileMenu" :class="{ 'active': isMobileMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <div class="nav-links" :class="{ 'mobile-open': isMobileMenuOpen }">
        <a href="#about" class="nav-link hover-scale">О продукте</a>
        <a href="#sales" class="nav-link hover-scale">Точки продажи</a>
        <a href="#benefits" class="nav-link hover-scale">Преимущества</a>
        <a href="#media" class="nav-link hover-scale">Медиа</a>
        <a href="#contacts" class="nav-link hover-scale">Контакты</a>
        
        <div class="nav-contact-info">
          <a href="tel:+998977574488" class="nav-contact-link">
            +998 97 757 44 88
          </a>
          <div class="nav-social">
            <a href="https://instagram.com/seven_dates.uz" target="_blank" class="nav-social-link" title="Instagram">
              <svg class="nav-icon" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
            </a>
            <a href="https://t.me/sevendates" target="_blank" class="nav-social-link" title="Telegram">
              <svg class="nav-icon" viewBox="0 0 24 24" fill="currentColor">
                <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navigation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 0.8rem 0;
  transition: all 0.3s ease;
  background: rgba(46, 74, 47, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: var(--shadow-lg);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.navigation.scrolled {
  transform: translateY(0);
}

.nav-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-family: var(--font-secondary);
  font-size: 1.5rem;
  font-weight: 700;
  text-decoration: none;
  color: var(--color-secondary);
}

.logo::after {
  display: none;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.nav-link {
  color: var(--color-white);
  font-weight: 500;
  text-decoration: none;
  padding: 0.5rem 0.8rem;
  border-radius: var(--radius-md);
  transition: all 0.3s ease;
  font-size: 0.9rem;
  white-space: nowrap;
}

.nav-link:hover {
  color: var(--color-secondary);
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
}

.mobile-menu-btn span {
  width: 100%;
  height: 2px;
  background: var(--color-white);
  transition: all 0.3s ease;
}

.mobile-menu-btn.active span:nth-child(1) {
  transform: translateY(9px) rotate(45deg);
}

.mobile-menu-btn.active span:nth-child(2) {
  opacity: 0;
}

.mobile-menu-btn.active span:nth-child(3) {
  transform: translateY(-9px) rotate(-45deg);
}

@media (max-width: 768px) {
  .mobile-menu-btn {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 0;
    right: -100%;
    width: 100%;
    height: 100vh;
    background: var(--gradient-primary);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
    gap: var(--space-lg);
  }

  .nav-links.mobile-open {
    right: 0;
  }

  .nav-link {
    font-size: 1.2rem;
  }

  .nav-contact-info {
    flex-direction: column;
    margin: 2rem 0 0 0;
    padding: 2rem 0 0 0;
    border-left: none;
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    width: 100%;
    align-items: center;
  }

  .nav-social {
    margin-top: 1rem;
  }

  .nav-contact-link {
    font-size: 1rem;
  }

  .nav-social-link {
    width: 36px;
    height: 36px;
  }

  .nav-icon {
    width: 18px;
    height: 18px;
  }
}

@media (max-width: 480px) {
  .logo {
    font-size: 1.5rem;
  }
}

.nav-contact-info {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-left: 1rem;
  padding-left: 1rem;
  border-left: 1px solid rgba(255, 255, 255, 0.2);
}

.nav-contact-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--color-white);
  text-decoration: none;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  white-space: nowrap;
}

.nav-contact-link:hover {
  color: var(--color-secondary);
}

.nav-social {
  display: flex;
  align-items: center;
  gap: 0.8rem;
}

.nav-social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  color: var(--color-white);
  transition: all 0.3s ease;
}

.nav-social-link:hover {
  background: var(--color-secondary);
  transform: translateY(-2px);
}

.nav-icon {
  width: 14px;
  height: 14px;
}
</style> 