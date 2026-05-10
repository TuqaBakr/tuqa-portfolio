<script setup lang="ts">
defineProps<{
  isArabic: boolean
}>()
</script>

<template>
  <footer id="contact" class="bg-surface-light dark:bg-surface-dark pt-12 pb-28 md:pb-12 border-t border-gray-200 dark:border-gray-800 transition-colors duration-300 mt-20 relative overflow-hidden">
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

      <div class="flex flex-col items-center text-gray-600 dark:text-gray-300 text-sm gap-4" :class="isArabic ? 'md:items-start' : 'md:items-start'">
         <a href="mailto:tuqabakr098@gmail.com" class="hover:text-brand-accent font-semibold text-base transition-colors flex items-center gap-2">
           ✉️ tuqabakr098@gmail.com
         </a>
         
         <div class="flex flex-wrap justify-center gap-5 font-bold" :class="isArabic ? 'flex-row-reverse' : ''">
           
           <a href="https://wa.me/963945052098" target="_blank" rel="noopener noreferrer" class="flex items-center gap-1.5 text-gray-700 dark:text-gray-300 hover:text-[#25D366] dark:hover:text-[#25D366] transition-colors">
             <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
               <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 0 0-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413Z"/>
             </svg>
             WhatsApp
           </a>

           <a href="https://t.me/TuQa_Bakr" target="_blank" rel="noopener noreferrer" class="flex items-center gap-1.5 text-gray-700 dark:text-gray-300 hover:text-[#229ED9] dark:hover:text-[#229ED9] transition-colors">
             <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
               <path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.894 8.221l-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.446 1.394c-.14.18-.357.223-.548.223l.188-2.85 5.18-4.686c.223-.198-.054-.31-.346-.11l-6.4 4.024-2.76-.86c-.6-.185-.61-.6.125-.89l10.736-4.135c.498-.184.935.115.753.864z"/>
             </svg>
             Telegram
           </a>
           
           <span class="text-gray-400 font-normal hidden sm:inline">|</span>
           
           <span class="flex items-center gap-1.5 w-full sm:w-auto justify-center">📞 (+963) 938 925 509</span>
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