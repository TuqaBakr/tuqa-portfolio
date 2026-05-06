<script setup lang="ts">
defineProps<{
  isArabic: boolean
}>()
</script>

<template>
  <footer class="bg-surface-light dark:bg-surface-dark py-12 border-t border-gray-200 dark:border-gray-800 transition-colors duration-300 mt-20 relative overflow-hidden">
    <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-brand to-brand-accent"></div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center gap-8" :dir="isArabic ? 'rtl' : 'ltr'">

      <div class="text-center" :class="isArabic ? 'md:text-right' : 'md:text-left'">
        <span class="font-bold text-3xl tracking-tight text-brand dark:text-brand-accent">
          {{ isArabic ? 'تقى.' : 'Tuqa.dev' }}
        </span>
        <p class="text-gray-500 dark:text-gray-400 mt-2 text-sm font-medium">
          {{ isArabic ? '© 2026 تقى حسين بكر. مطورة برمجيات.' : '© 2026 Tuqa Hussen Baker. Software Engineer.' }}
        </p>
      </div>

      <div class="flex flex-col items-center text-gray-600 dark:text-gray-300 text-sm gap-3" :class="isArabic ? 'md:items-start' : 'md:items-start'">
         <a href="mailto:tuqabakr098@gmail.com" class="hover:text-brand-accent font-semibold text-base transition-colors flex items-center gap-2">
           ✉️ tuqabakr098@gmail.com
         </a>
         <div class="flex gap-4 font-medium" :class="isArabic ? 'flex-row-reverse' : ''">
           <span>📞 (+963) 945 052 098</span>
           <span class="text-gray-400">|</span>
           <span>(+963) 938 925 509</span>
         </div>
         <span class="text-gray-500 dark:text-gray-400 font-medium">
           📍 {{ isArabic ? 'دمشق، سوريا' : 'Damascus, Syria' }}
         </span>
      </div>

      <div class="flex gap-4" :class="{ 'flex-row-reverse': isArabic }">
         <a href="https://www.linkedin.com/in/tuqa-baker-6094a6240" target="_blank" class="px-5 py-2.5 rounded-lg bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-brand hover:text-white dark:hover:bg-brand-accent dark:hover:text-brand-dark transition-all font-bold text-sm shadow-sm">
           LinkedIn
         </a>
         <a href="https://github.com/TuqaBakr" target="_blank" class="px-5 py-2.5 rounded-lg bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-brand hover:text-white dark:hover:bg-brand-accent dark:hover:text-brand-dark transition-all font-bold text-sm shadow-sm">
           GitHub
         </a>
         <a href="https://gitlab.com/tuqabakr098" target="_blank" class="px-5 py-2.5 rounded-lg bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-brand hover:text-white dark:hover:bg-brand-accent dark:hover:text-brand-dark transition-all font-bold text-sm shadow-sm">
           GitLab
         </a>
      </div>

    </div>
  </footer>
</template>