<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-section">
        <div class="logo">
          <h3>Seven Dates</h3>
        </div>
        <p class="company-description">
          Натуральный финиковый напиток премиум-класса из Италии. 
          Производство с соблюдением высочайших стандартов качества.
        </p>
      </div>

      <div class="footer-section">
        <h4>Навигация</h4>
        <ul class="footer-links">
          <li><a href="#about">О продукте</a></li>
          <li><a href="#sales">Точки продажи</a></li>
          <li><a href="#benefits">Преимущества</a></li>
          <li><a href="#media">Медиа</a></li>
        </ul>
      </div>

      <div class="footer-section">
        <h4>Контакты</h4>
        <ul class="contact-list">
          <li>
            <span class="icon">📍</span>
            г. Ташкент, Сергелийский район,<br>
            ул. Олтин Водий 3-тупик, 111
          </li>
          <li>
            <span class="icon">📞</span>
            <a href="tel:+998977574488">+998 97 757 44 88</a>
          </li>
          <li>
            <span class="icon">✉️</span>
            <strong>Для сотрудничества:</strong><br>
            <a href="mailto:partner@sevendates.uz">partner@sevendates.uz</a>
          </li>
          <li>
            <span class="icon">✉️</span>
            <strong>Общие вопросы:</strong><br>
            <a href="mailto:info@sevendates.uz">info@sevendates.uz</a>
          </li>
        </ul>
      </div>

      <div class="footer-section">
        <h4>Социальные сети</h4>
        <div class="social-links">
          <a href="https://instagram.com/seven_dates.uz" target="_blank" class="social-link">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
            Instagram
          </a>
          <a href="https://t.me/sevendatesuz" target="_blank" class="social-link">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
            </svg>
            Telegram
              </a>
            </div>
          </div>
        </div>

    <div class="footer-bottom">
      <div class="container">
        <p>&copy; 2025 Seven Dates. Все права защищены.</p>
        <div class="footer-extra-links">
          <a href="#">Политика конфиденциальности</a>
          <span class="divider">|</span>
          <a href="#">Условия использования</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: rgb(25, 62, 29);
  color: white;
  padding-top: 4rem;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
  margin-bottom: 3rem;
}

.footer-section {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.logo h3 {
  font-family: var(--font-secondary);
  font-size: 2rem;
  font-weight: bold;
  color: rgb(239, 205, 158);
  margin: 0;
}

.company-description {
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.6;
  font-size: 0.95rem;
}

.footer-section h4 {
  color: rgb(239, 205, 158);
  font-size: 1.2rem;
  margin: 0;
  font-weight: bold;
  font-family: var(--font-secondary);
}

.footer-links,
.contact-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.footer-links a,
.contact-list a {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover,
.contact-list a:hover {
  color: rgb(239, 205, 158);
}

.contact-list li {
  display: flex;
  align-items: flex-start;
  gap: 0.8rem;
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.95rem;
}

.icon {
  font-size: 1.2rem;
  flex-shrink: 0;
  color: rgb(239, 205, 158);
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.social-icon {
  width: 24px;
  height: 24px;
  transition: transform 0.3s ease;
  color: rgb(239, 205, 158);
}

.social-link:hover .social-icon {
  transform: scale(1.1);
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: all 0.3s ease;
  padding: 0.8rem;
  border-radius: 8px;
  font-size: 1rem;
}

.social-link:hover {
  color: rgb(239, 205, 158);
  background: rgba(239, 205, 158, 0.1);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 1.5rem 0;
  background: rgba(0, 0, 0, 0.2);
}

.footer-bottom .container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.6);
}

.footer-extra-links {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.footer-extra-links a {
  color: rgba(255, 255, 255, 0.6);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-extra-links a:hover {
  color: rgb(239, 205, 158);
}

.divider {
  color: rgba(255, 255, 255, 0.3);
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .footer-bottom .container {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }

  .footer-extra-links {
    flex-direction: column;
    gap: 0.5rem;
  }

  .divider {
    display: none;
  }
}
</style> 