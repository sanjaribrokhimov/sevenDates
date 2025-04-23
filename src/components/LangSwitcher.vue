<script setup>
import { ref, onMounted, watch } from 'vue'
import { useTranslations } from '../stores/translations'

const { setLanguage, getCurrentLanguage } = useTranslations()
const currentLang = ref(getCurrentLanguage())

// Функция для изменения языка
const changeLanguage = (lang) => {
  if (lang === currentLang.value) return
  currentLang.value = lang
  setLanguage(lang)
  // Перезагрузка страницы для применения изменений
  window.location.reload()
}

// Инициализация при монтировании компонента
onMounted(() => {
  const savedLang = localStorage.getItem('preferred_language')
  if (savedLang && (savedLang === 'ru' || savedLang === 'uz')) {
    currentLang.value = savedLang
    setLanguage(savedLang)
  }
})

// Следим за изменениями языка
watch(currentLang, (newLang) => {
  document.documentElement.lang = newLang
})
</script>

<template>
  <div class="language-switcher">
    <button 
      @click="changeLanguage('ru')" 
      :class="{ active: currentLang === 'ru' }"
      class="lang-btn"
    >
      RU
    </button>
    <button 
      @click="changeLanguage('uz')" 
      :class="{ active: currentLang === 'uz' }"
      class="lang-btn"
    >
      UZ
    </button>
  </div>
</template>

<style scoped>
.language-switcher {
  display: flex;
  gap: 0.5rem;
  align-items: center;
}

.lang-btn {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: rgb(25, 62, 29);
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 0.9rem;
}

.lang-btn:hover {
  background: rgba(255, 255, 255, 0.2);
}

.lang-btn.active {
  background: white;
  color: rgb(25, 62, 29);
  font-weight: 600;
}
</style>
