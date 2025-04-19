<template>
  <section id="sales" class="sales-section">
    <div class="container">
      <h2 class="section-title animate-on-scroll">
        Точки продаж в Ташкенте
      </h2>
      <p class="section-description animate-on-scroll">
        Вы можете приобрести Seven Dates в сети магазинов MAKRO
      </p>

      <div class="sales-content">
        <div class="map-container animate-on-scroll">
          <div class="map-placeholder">
            <iframe 
              src="https://www.openstreetmap.org/export/embed.html?bbox=69.1796875%2C41.2545%2C69.3359375%2C41.3545&amp;layer=mapnik&amp;marker=41.304559%2C69.257812"
              style="width: 100%; height: 100%; border: none;"
              loading="lazy"
            ></iframe>
          </div>
        </div>

        <div class="locations-grid">
          <div class="location-card animate-on-scroll">
            <div class="location-icon">📍</div>
            <h3>MAKRO ЦУМ</h3>
            <p class="address">ул. Узбекистанская (ориентир: кафе BIBIGON)</p>
            <p class="work-hours">09:00 - 23:00</p>
            <a href="https://maps.google.com/?q=41.311559,69.267779" target="_blank" class="map-link">Открыть на карте →</a>
          </div>

          <div class="location-card animate-on-scroll">
            <div class="location-icon">📍</div>
            <h3>MAKRO Нукусская</h3>
            <p class="address">ул. Нукусская</p>
            <p class="work-hours">09:00 - 23:00</p>
            <a href="https://maps.google.com/?q=41.325543,69.228745" target="_blank" class="map-link">Открыть на карте →</a>
          </div>

          <div class="location-card animate-on-scroll">
            <div class="location-icon">📍</div>
            <h3>MAKRO Махтумкули</h3>
            <p class="address">ул. Махтумкули, 134</p>
            <p class="work-hours">09:00 - 23:00</p>
            <a href="https://maps.google.com/?q=41.288595,69.254444" target="_blank" class="map-link">Открыть на карте →</a>
          </div>

          <div class="location-card animate-on-scroll">
            <div class="location-icon">📍</div>
            <h3>MAKRO Саехат</h3>
            <p class="address">Гостиница Саехат</p>
            <p class="work-hours">09:00 - 23:00</p>
            <a href="https://maps.google.com/?q=41.302675,69.254165" target="_blank" class="map-link">Открыть на карте →</a>
          </div>

          <div class="location-card animate-on-scroll">
            <div class="location-icon">📍</div>
            <h3>MAKRO Аэропорт</h3>
            <p class="address">Корейский аэропорт</p>
            <p class="work-hours">09:00 - 23:00</p>
            <a href="https://maps.google.com/?q=41.283333,69.267778" target="_blank" class="map-link">Открыть на карте →</a>
          </div>

          <div class="location-card animate-on-scroll coming-soon">
            <div class="location-icon">🔜</div>
            <h3>Скоро открытие</h3>
            <p class="address">Новые магазины MAKRO</p>
            <p class="work-hours">Следите за обновлениями</p>
            <span class="coming-soon-label">Скоро</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.sales-section {
  padding: 6rem 0;
  background: #f8f9f8;
  position: relative;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: var(--color-primary);
  font-family: var(--font-secondary);
}

.section-description {
  text-align: center;
  font-size: 1.2rem;
  margin-bottom: 4rem;
  color: var(--color-text);
  opacity: 0.8;
}

.sales-content {
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

.map-container {
  width: 100%;
  height: 500px;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.map-placeholder {
  width: 100%;
  height: 100%;
  background: #f0f0f0;
}

.locations-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.location-card {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(46, 74, 47, 0.1);
  position: relative;
}

.location-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.location-icon {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  color: var(--color-primary);
}

.location-card h3 {
  font-size: 1.3rem;
  color: var(--color-primary);
  margin-bottom: 1rem;
  font-family: var(--font-secondary);
}

.address {
  color: var(--color-text);
  margin-bottom: 0.5rem;
  font-size: 1rem;
}

.work-hours {
  color: var(--color-text);
  opacity: 0.8;
  margin-bottom: 1.5rem;
  font-size: 0.9rem;
}

.map-link {
  display: inline-block;
  color: var(--color-primary);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.map-link:hover {
  color: var(--color-secondary);
  transform: translateX(5px);
}

.coming-soon {
  background: linear-gradient(135deg, rgba(255,255,255,0.9), rgba(255,255,255,0.95));
  border: 2px dashed var(--color-secondary);
}

.coming-soon-label {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: var(--color-secondary);
  color: white;
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
}

@media (max-width: 1200px) {
  .locations-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .sales-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
  }

  .section-description {
    font-size: 1.1rem;
    margin-bottom: 3rem;
  }

  .map-container {
    height: 300px;
  }

  .locations-grid {
    grid-template-columns: 1fr;
  }

  .location-card {
    padding: 1.5rem;
  }
}

.map-overlay {
  position: absolute;
  top: 20px;
  right: 20px;
  background: rgba(255, 255, 255, 0.9);
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.map-legend {
  font-size: 0.9rem;
}

.map-legend h4 {
  margin-bottom: 10px;
  color: var(--color-primary);
}

.map-legend ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.map-legend li {
  margin-bottom: 8px;
  display: flex;
  align-items: center;
  gap: 8px;
}

.marker {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  background: #ff4444;
  color: white;
  border-radius: 50%;
  font-size: 0.8rem;
  font-weight: bold;
}
</style> 