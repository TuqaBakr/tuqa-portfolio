<script setup lang="ts">
defineProps<{
  isArabic: boolean
}>()

// We store the data in an array to keep the template clean
const timelineData = [
  {
    dateEn: 'Oct 2025 - Present',
    dateAr: 'أكتوبر 2025 - الحاضر',
    titleEn: 'Flutter Developer',
    titleAr: 'مطور فلاتر',
    companyEn: 'MTS Company',
    companyAr: 'شركة MTS',
    descriptionEn: 'Engineering multiple application variants using Flutter Flavors, optimizing Android TV streaming, and managing Google Play deployments.',
    descriptionAr: 'هندسة نسخ متعددة من التطبيقات باستخدام Flutter Flavors، وتحسين بث الفيديو على Android TV، وإدارة عمليات النشر على Google Play.',
    icon: '💻'
  },
  {
    dateEn: 'Jun 2025 - Aug 2025',
    dateAr: 'يونيو 2025 - أغسطس 2025',
    titleEn: 'Flutter Developer',
    titleAr: 'مطور فلاتر',
    companyEn: 'Event Halls Management System',
    companyAr: 'نظام إدارة صالات المناسبات',
    descriptionEn: 'Automated the reservation process across dual mobile applications, increasing operational efficiency by 30% using Clean Architecture and Bloc.',
    descriptionAr: 'أتمتة عملية الحجز عبر تطبيقات هواتف مزدوجة، مما زاد من الكفاءة التشغيلية بنسبة 30٪ باستخدام Clean Architecture و Bloc.',
    icon: '📱'
  },
  {
    dateEn: 'Graduated 2025',
    dateAr: 'تخرج 2025',
    titleEn: "Bachelor's in Software Engineering",
    titleAr: 'إجازة في هندسة البرمجيات ونظم المعلومات',
    companyEn: 'University of Damascus',
    companyAr: 'جامعة دمشق',
    descriptionEn: 'Faculty of Informatics Engineering. Applied Scrum methodology, created comprehensive SRS documentation, and performed Function Point estimation.',
    descriptionAr: 'كلية الهندسة المعلوماتية. تطبيق منهجية Scrum، وإنشاء وثائق SRS شاملة، وإجراء تقدير نقاط الوظيفة (Function Point).',
    icon: '🎓'
  }
]
</script>

<template>
  <section id="experience" class="py-20 bg-brand-light dark:bg-brand-dark transition-colors duration-300">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <div class="text-center mb-16">
        <h2 class="text-4xl font-extrabold text-brand dark:text-white">
          {{ isArabic ? 'الخبرات والتعليم' : 'Experience & Education' }}
        </h2>
        <div class="w-24 h-1 bg-brand-accent mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="relative border-gray-300 dark:border-gray-700" 
           :class="isArabic ? 'border-r-4 pr-8 ml-auto text-right' : 'border-l-4 pl-8 mr-auto text-left'">
        
        <div v-for="(item, index) in timelineData" :key="index" class="mb-12 relative">
          
          <div class="absolute top-0 w-8 h-8 bg-brand-accent rounded-full flex items-center justify-center shadow-lg border-4 border-brand-light dark:border-brand-dark"
               :class="isArabic ? '-right-[42px]' : '-left-[42px]'">
            <span class="text-sm">{{ item.icon }}</span>
          </div>

          <div class="bg-surface-light dark:bg-surface-dark p-6 rounded-2xl shadow-md border border-gray-100 dark:border-gray-800 hover:shadow-xl transition-shadow">
            <span class="text-sm font-bold text-brand-accent tracking-wider uppercase mb-2 block">
              {{ isArabic ? item.dateAr : item.dateEn }}
            </span>
            <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-1">
              {{ isArabic ? item.titleAr : item.titleEn }}
            </h3>
            <h4 class="text-lg font-medium text-brand dark:text-gray-400 mb-4">
              {{ isArabic ? item.companyAr : item.companyEn }}
            </h4>
            <p class="text-gray-600 dark:text-gray-300 leading-relaxed">
              {{ isArabic ? item.descriptionAr : item.descriptionEn }}
            </p>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>