<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  isArabic: boolean
}>()

// State to track which image is currently clicked/focused
const selectedImage = ref<string | null>(null)

// A dynamic array makes it incredibly easy to add or remove projects later
const projectsList = [
  {
    titleEn: 'MTS & Alfateh TV Applications',
    titleAr: 'تطبيقات MTS و Alfateh TV',
    descEn: 'Developed and optimized Android TV applications, integrating robust video players and live streaming functionalities using Flutter Flavors.',
    descAr: 'تطوير وتحسين تطبيقات Android TV، ودمج مشغلات فيديو قوية ووظائف البث المباشر باستخدام Flutter Flavors.',
    tags: ['Flutter', 'Android TV', 'Video Streaming'],
    images: [
      '/projects/mts/app_icon.jpeg', 
      '/projects/mts/mts1.png', 
      '/projects/mts/mts2.png', 
      '/projects/mts/mts3.png',
      '/projects/mts/mts4.png',
      '/projects/mts/mts5.png',
      '/projects/mts/mts6.png',
      '/projects/mts/mts7.png',
      '/projects/mts/mts8.png',
      '/projects/mts/mts9.png',
      '/projects/mts/mts10.png'
    ]
  },
  {
    titleEn: 'Event Halls Management System',
    titleAr: 'نظام إدارة صالات المناسبات',
    descEn: 'Automated the entire reservation process across dual mobile applications, increasing operational efficiency by 30%. Implemented advanced geolocation filtering.',
    descAr: 'أتمتة عملية حجز الصالات بالكامل عبر تطبيقات هواتف مزدوجة، مما أدى إلى زيادة الكفاءة التشغيلية بنسبة 30٪.',
    tags: ['Clean Architecture', 'Bloc', 'Google Maps API'],
    srsLink: '/projects/book_it/srs.pdf', 
    presLink: '/projects/book_it/pres.pptm', // <-- Added the presentation link here!
    images: [
      '/projects/book_it/logo.png',
      '/projects/book_it/bookit0.png',
      '/projects/book_it/bookit00.png',
      '/projects/book_it/bookit000.png',
      '/projects/book_it/bookit0000.png',
      '/projects/book_it/bookit1.png',
      '/projects/book_it/bookit2.png',
      '/projects/book_it/bookit3.png',
      '/projects/book_it/bookit4.png',
      '/projects/book_it/bookit5.png',
      '/projects/book_it/bookit6.png',
      '/projects/book_it/bookit7.png',
      '/projects/book_it/bookit8.png',
      '/projects/book_it/bookit9.png',
      '/projects/book_it/bookit10.png',
      '/projects/book_it/bookit11.png',
      '/projects/book_it/bookit12.png',
      '/projects/book_it/bookit13.png',
      '/projects/book_it/bookit14.png',
      '/projects/book_it/bookit15.png',
      '/projects/book_it/bookit16.png',
      '/projects/book_it/bookit17.png',
      '/projects/book_it/bookit18.png'
    ]
  },
  {
    titleEn: 'Medical Centre Automation',
    titleAr: 'أتمتة المركز الطبي',
    descEn: 'Developed a suite of multi-role patient and physician apps reducing manual scheduling tasks by 40%. Integrated secure video consultations.',
    descAr: 'تطوير مجموعة من تطبيقات المرضى والأطباء متعددة الأدوار مما قلل مهام الجدولة اليدوية بنسبة 40٪. يتضمن استشارات فيديو آمنة.',
    tags: ['Flutter', 'Healthcare Privacy', 'Video Consultation'],
    srsLink: '/projects/medical_center/srs.pdf', // <-- Updated to your specific medical_center folder
    images: [
      '/projects/medical_center/logo.jpg', 
    ]
  },
  {
    titleEn: 'Stupify E-commerce (Dimo)',
    titleAr: 'تطبيق التجارة الإلكترونية Stupify',
    descEn: 'Launched a feature-rich e-commerce application with advanced search, product reviews, and multi-lingual support, utilizing GetX.',
    descAr: 'إطلاق تطبيق تجارة إلكترونية غني بالميزات مع بحث متقدم وتقييمات المنتجات ودعم متعدد اللغات باستخدام GetX.',
    tags: ['GetX', 'MVC', 'REST APIs'],
    // SRS link removed completely for Shopify!
    images: [
       '/projects/spotify/spotify0.png',
      '/projects/spotify/spotify1.png',
      '/projects/spotify/spotify2.png',
      '/projects/spotify/spotify3.png',
      '/projects/spotify/spotify4.png',
      '/projects/spotify/spotify5.png',
      '/projects/spotify/spotify6.png',
      '/projects/spotify/spotify7.png',
      '/projects/spotify/spotify8.png',
      '/projects/spotify/spotify9.png'
    ]
  }
]
</script>

<template>
  <section id="projects" class="py-20 bg-surface-light dark:bg-surface-dark transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <div class="text-center mb-16">
        <h2 class="text-4xl font-extrabold text-brand dark:text-white">
          {{ isArabic ? 'كل المشاريع' : 'All Projects' }}
        </h2>
        <div class="w-24 h-1 bg-brand-accent mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-10" :dir="isArabic ? 'rtl' : 'ltr'">
        
        <div v-for="(project, index) in projectsList" :key="index" class="bg-brand-light dark:bg-brand-dark rounded-2xl border border-gray-200 dark:border-gray-800 overflow-hidden shadow-lg hover:shadow-xl transition-shadow flex flex-col">
          
          <div class="relative w-full h-72 bg-gray-900 group">
            <div class="flex overflow-x-auto snap-x snap-mandatory h-full hide-scrollbar">
              <div v-for="(img, i) in project.images" :key="i" class="min-w-full h-full snap-center flex items-center justify-center p-4">
                
                <img 
                  :src="img" 
                  :alt="project.titleEn" 
                  class="max-h-full max-w-full object-contain drop-shadow-2xl rounded-lg cursor-pointer hover:opacity-80 transition-opacity" 
                  @click="selectedImage = img"
                  onerror="this.style.display='none'; this.nextElementSibling.style.display='block';" 
                />
                
                <div class="hidden text-center text-gray-400 font-medium text-sm">
                  Missing Image: <br/> <span class="text-brand-accent">{{ img }}</span>
                </div>

              </div>
            </div>
            <div class="absolute bottom-2 right-2 bg-black/60 text-white text-xs px-2 py-1 rounded-full pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity">
              {{ isArabic ? 'اسحب للمزيد أو اضغط للتكبير' : 'Swipe for more / Click to expand' }}
            </div>
          </div>

          <div class="p-8 flex-grow flex flex-col">
            <div class="flex flex-col xl:flex-row justify-between items-start mb-4 gap-4">
              <h3 class="text-2xl font-bold text-gray-900 dark:text-white">
                {{ isArabic ? project.titleAr : project.titleEn }}
              </h3>
              
              <!-- Container for Document Buttons -->
              <div class="flex flex-wrap gap-2">
                <!-- Presentation Button -->
                <a v-if="project.presLink" :href="project.presLink" target="_blank" class="flex-shrink-0 flex items-center gap-1 px-3 py-1.5 bg-blue-500/10 text-blue-600 dark:text-blue-400 rounded-md hover:bg-blue-600 hover:text-white transition-colors text-sm font-bold border border-blue-500/20">
                  📊 {{ isArabic ? 'عرض تقديمي' : 'Presentation' }}
                </a>
                
                <!-- SRS Document Button -->
                <a v-if="project.srsLink" :href="project.srsLink" target="_blank" class="flex-shrink-0 flex items-center gap-1 px-3 py-1.5 bg-brand/10 dark:bg-brand-accent/10 text-brand dark:text-brand-accent rounded-md hover:bg-brand hover:text-white dark:hover:bg-brand-accent dark:hover:text-brand-dark transition-colors text-sm font-bold border border-brand/20">
                  📄 {{ isArabic ? 'وثيقة SRS' : 'View SRS' }}
                </a>
              </div>
            </div>
            
            <p class="text-gray-600 dark:text-gray-300 mb-6 flex-grow leading-relaxed">
              {{ isArabic ? project.descAr : project.descEn }}
            </p>
            
            <div class="flex flex-wrap gap-2 mt-auto pt-4 border-t border-gray-200 dark:border-gray-700">
              <span v-for="tag in project.tags" :key="tag" class="px-3 py-1 bg-surface-light dark:bg-surface-dark text-brand dark:text-brand-accent rounded-md text-xs font-bold border border-gray-200 dark:border-gray-600 shadow-sm">
                {{ tag }}
              </span>
            </div>
          </div>

        </div>
      </div>

    </div>

    <!-- Full Screen Lightbox Modal -->
    <div 
      v-if="selectedImage" 
      class="fixed inset-0 z-[100] bg-black/90 flex items-center justify-center p-4 backdrop-blur-sm"
      @click="selectedImage = null"
    >
      <button class="absolute top-6 right-6 text-white hover:text-brand-accent text-5xl transition-colors font-light">
        &times;
      </button>
      <img :src="selectedImage" class="max-w-full max-h-[90vh] object-contain rounded-lg shadow-2xl" @click.stop />
    </div>

  </section>
</template>

<style scoped>
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>