<script setup lang="ts">
defineProps<{
  isArabic: boolean
}>()

// Categorized skills to make it easily readable for recruiters
const skillCategories = [
  {
    titleEn: 'Languages & Frameworks',
    titleAr: 'اللغات وإطارات العمل',
    skills: ['Flutter (Dart)', 'Java', 'C++', 'Vue.js']
  },
  {
    titleEn: 'Architecture & Patterns',
    titleAr: 'الهيكلية وأنماط التصميم',
    skills: ['Clean Architecture', 'SOLID Principles', 'MVC', 'Flutter Flavors']
  },
  {
    titleEn: 'State Management',
    titleAr: 'إدارة الحالة',
    skills: ['Bloc', 'Cubit', 'GetX']
  },
  {
    titleEn: 'Backend & Integrations',
    titleAr: 'الواجهة الخلفية والتكامل',
    skills: ['Firebase', 'REST APIs', 'Socket.io', 'OpenStreetMap']
  }
]
</script>

<template>
  <section id="skills" class="py-20 bg-surface-light dark:bg-surface-dark transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <div class="text-center mb-16">
        <h2 class="text-4xl font-extrabold text-brand dark:text-white">
          {{ isArabic ? 'المهارات التقنية' : 'Technical Skills' }}
        </h2>
        <div class="w-24 h-1 bg-brand-accent mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8" :dir="isArabic ? 'rtl' : 'ltr'">
        <div 
          v-for="(category, index) in skillCategories" 
          :key="index" 
          class="bg-brand-light dark:bg-brand-dark p-6 rounded-2xl shadow-sm border border-gray-100 dark:border-gray-800 hover:shadow-md transition-shadow"
        >
          <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-4 border-b border-brand/20 pb-2">
            {{ isArabic ? category.titleAr : category.titleEn }}
          </h3>
          <div class="flex flex-wrap gap-2">
            <span 
              v-for="skill in category.skills" 
              :key="skill" 
              class="px-3 py-1 bg-white dark:bg-surface-dark text-brand dark:text-brand-accent rounded-md text-sm font-medium shadow-sm border border-gray-100 dark:border-gray-700"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>