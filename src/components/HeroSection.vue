<script setup lang="ts">
defineProps<{
  isArabic: boolean
}>()
</script>

<template>
  <section id="about" class="pt-32 pb-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center gap-12" :dir="isArabic ? 'rtl' : 'ltr'">
    
    <div class="w-56 h-56 md:w-80 md:h-80 flex-shrink-0 relative fade-in">
       <div class="absolute inset-0 bg-brand dark:bg-brand-accent rounded-full transform translate-x-4 translate-y-4 opacity-20"></div>
       <img 
         src="/profile.jpg" 
         alt="Tuqa Hussen Baker" 
         class="w-full h-full object-cover rounded-full border-4 border-surface-light dark:border-surface-dark relative z-10 shadow-xl bg-gray-200 dark:bg-gray-800" 
       />
    </div>

    <div class="text-center md:text-start fade-in" :class="isArabic ? 'md:text-right' : 'md:text-left'" style="animation-delay: 0.2s;">
      <h1 class="text-5xl md:text-6xl font-extrabold text-brand dark:text-white mb-6">
        {{ isArabic ? 'مرحباً، أنا تقى حسين بكر' : 'Hi, I am Tuqa Hussen Baker' }}
      </h1>
      <p class="text-xl text-gray-600 dark:text-gray-300 mb-8 leading-relaxed">
        {{ isArabic
           ? 'مهندسة برمجيات ومطورة تطبيقات فلاتر بخبرة تزيد عن سنتين. متخصصة في بناء واجهات عالية الأداء وتطبيقات Android TV. شغوفة بالهيكلية النظيفة (Clean Architecture) وتقديم حلول برمجية قابلة للتوسع.'
           : 'Software Engineer & Flutter Developer with over 2 years of experience. Specializing in high-performance cross-platform mobile and Android TV applications. Passionate about Clean Architecture and delivering scalable solutions.' 
        }}
      </p>
      
      <div class="flex flex-wrap gap-4 justify-center" :class="isArabic ? 'md:justify-start' : 'md:justify-start'">
        <a href="#projects" class="px-8 py-3 bg-brand text-white rounded-lg hover:bg-brand-accent transition-colors font-bold shadow-lg">
          {{ isArabic ? 'عرض مشاريعي' : 'View My Work' }}
        </a>
        <a href="/cv.pdf" target="_blank" class="px-8 py-3 bg-surface-light dark:bg-surface-dark text-brand dark:text-white border-2 border-brand dark:border-gray-600 rounded-lg hover:border-brand-accent transition-colors font-bold shadow-sm">
          {{ isArabic ? 'تحميل السيرة الذاتية' : 'Download CV' }}
        </a>
      </div>
    </div>

  </section>
</template>

<style scoped>
.fade-in {
  animation: fadeIn 1s ease-out backwards;
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>