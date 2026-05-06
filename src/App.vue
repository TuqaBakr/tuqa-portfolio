<script setup lang="ts">
import { ref, watchEffect } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue' // <-- Imported Hero
import SkillsSection from './components/SkillsSection.vue' 
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue' 
import FooterSection from './components/FooterSection.vue' 

const isDark = ref(true)
const isArabic = ref(false)

watchEffect(() => {
  if (isDark.value) {
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
})

watchEffect(() => {
  document.documentElement.dir = isArabic.value ? 'rtl' : 'ltr'
})

const toggleTheme = () => isDark.value = !isDark.value
const toggleLanguage = () => isArabic.value = !isArabic.value
</script>

<template>
  <div class="min-h-screen bg-brand-light dark:bg-brand-dark text-gray-900 dark:text-gray-100 transition-colors duration-300 font-sans flex flex-col">
    
    <NavBar 
      :isDark="isDark" 
      :isArabic="isArabic" 
      @toggleTheme="toggleTheme" 
      @toggleLanguage="toggleLanguage" 
    />
    
    <main class="flex-grow">
      
      <HeroSection :isArabic="isArabic" />

      <SkillsSection :isArabic="isArabic" />

      <ExperienceSection :isArabic="isArabic" />

      <ProjectsSection :isArabic="isArabic" />

    </main>

    <FooterSection :isArabic="isArabic" />

  </div>
</template>

<style>
/* Global styles can stay here if needed */
</style>