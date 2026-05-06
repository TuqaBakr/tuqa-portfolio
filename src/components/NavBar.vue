<script setup lang="ts">
// Define the properties this component accepts from the parent
defineProps<{
  isDark: boolean
  isArabic: boolean
}>()

// Define the actions this component can send back to the parent
defineEmits(['toggleTheme', 'toggleLanguage'])
</script>

<template>
  <nav class="fixed w-full top-0 z-50 bg-surface-light/80 dark:bg-surface-dark/80 backdrop-blur-md border-b border-gray-200 dark:border-brand transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16 items-center">
        
        <div class="flex-shrink-0 font-bold text-2xl text-brand dark:text-brand-accent">
          <span v-if="isArabic">تقى.</span>
          <span v-else>Tuqa.dev</span>
        </div>

      <div class="hidden md:flex gap-8 items-center font-medium">
          <a href="#about" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'حول' : 'About' }}</a>
          <a href="#experience" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'الخبرات' : 'Experience' }}</a>
          <a href="#projects" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'المشاريع' : 'Projects' }}</a>
        </div>

        <div class="flex items-center gap-4">
          <button @click="$emit('toggleLanguage')" class="px-3 py-1.5 rounded-md bg-gray-200 dark:bg-brand font-bold text-sm hover:bg-gray-300 dark:hover:bg-brand-accent transition-colors">
            {{ isArabic ? 'EN' : 'عربي' }}
          </button>
          <button @click="$emit('toggleTheme')" class="p-2 rounded-full bg-gray-200 dark:bg-brand hover:bg-gray-300 dark:hover:bg-brand-accent transition-colors text-lg">
            <span v-if="isDark">☀️</span>
            <span v-else>🌙</span>
          </button>
        </div>

      </div>
    </div>
  </nav>
</template>