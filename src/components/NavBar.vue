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
      <div class="flex justify-between h-16 items-center" :dir="isArabic ? 'rtl' : 'ltr'">
        
        <div class="flex-shrink-0 font-bold text-2xl text-brand dark:text-brand-accent">
          <span v-if="isArabic">تقى.</span>
          <span v-else>Tuqa.dev</span>
        </div>

        <div class="hidden md:flex gap-8 items-center font-medium">
          <a href="#about" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'حول' : 'About' }}</a>
          <a href="#experience" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'الخبرات' : 'Experience' }}</a>
          <a href="#projects" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'المشاريع' : 'Projects' }}</a>
          <a href="#contact" class="hover:text-brand-accent transition-colors">{{ isArabic ? 'تواصل' : 'Contact' }}</a>
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

  <nav class="md:hidden fixed bottom-0 w-full z-50 bg-surface-light/95 dark:bg-surface-dark/95 backdrop-blur-xl border-t border-gray-200 dark:border-gray-800 transition-colors duration-300 shadow-[0_-4px_20px_rgba(0,0,0,0.1)]">
    <div class="flex justify-around items-center h-16 px-2" :dir="isArabic ? 'rtl' : 'ltr'">
      
      <a href="#about" class="flex flex-col items-center justify-center w-full h-full text-gray-500 dark:text-gray-400 hover:text-brand dark:hover:text-brand-accent active:scale-95 transition-all">
        <svg class="w-6 h-6 mb-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path>
        </svg>
        <span class="text-[10px] font-bold">{{ isArabic ? 'حول' : 'About' }}</span>
      </a>

      <a href="#experience" class="flex flex-col items-center justify-center w-full h-full text-gray-500 dark:text-gray-400 hover:text-brand dark:hover:text-brand-accent active:scale-95 transition-all">
        <svg class="w-6 h-6 mb-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
        </svg>
        <span class="text-[10px] font-bold">{{ isArabic ? 'الخبرات' : 'Experience' }}</span>
      </a>

      <a href="#projects" class="flex flex-col items-center justify-center w-full h-full text-gray-500 dark:text-gray-400 hover:text-brand dark:hover:text-brand-accent active:scale-95 transition-all">
        <svg class="w-6 h-6 mb-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z"></path>
        </svg>
        <span class="text-[10px] font-bold">{{ isArabic ? 'المشاريع' : 'Projects' }}</span>
      </a>

      <a href="#contact" class="flex flex-col items-center justify-center w-full h-full text-gray-500 dark:text-gray-400 hover:text-brand dark:hover:text-brand-accent active:scale-95 transition-all">
        <svg class="w-6 h-6 mb-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
        </svg>
        <span class="text-[10px] font-bold">{{ isArabic ? 'تواصل' : 'Contact' }}</span>
      </a>

    </div>
  </nav>
</template>