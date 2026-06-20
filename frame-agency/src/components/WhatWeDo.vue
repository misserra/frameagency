<template>
  <section id="services" class="px-16 py-8">
    <h2 class="font-merriweather font-light text-[clamp(2rem,4vw,3.875rem)] text-center mb-16">Что мы делаем</h2>

    <div class="grid grid-cols-2 gap-12 items-start">
      <!-- Accordion -->
      <div class="bg-[#ede9e9] rounded-[20px] border border-transparent px-10 py-6 space-y-4">
        <div v-for="item in items" :key="item.title">
          <button
            class="w-full flex items-center justify-between gap-6 py-2 text-left group"
            @click="toggle(item.title)"
          >
            <span class="font-merriweather font-light text-[2.2rem] leading-tight group-hover:opacity-70 transition-opacity">
              {{ item.title }}
            </span>
            <span class="text-3xl font-light text-neutral-500 shrink-0 transition-transform duration-300" :class="{ 'rotate-45': open === item.title }">
              +
            </span>
          </button>
          <div
            v-show="open === item.title"
            class="pb-4 font-inter font-light text-[1.1rem] leading-relaxed text-neutral-800"
          >
            {{ item.text }}
          </div>
          <hr class="border-black/20" />
        </div>
      </div>

      <!-- Images mosaic -->
      <div class="grid grid-cols-2 gap-3 h-125">
        <div class="flex flex-col gap-3">
          <img src="/static/images/collage_top_left.jpg" alt="" class="w-full h-[23%] object-cover" />
          <img src="/static/images/collage_bottom_left.jpg" alt="" class="w-full h-[55%] object-cover" />
        </div>
        <div class="flex flex-col gap-3">
          <img src="/static/images/collage_top_right.jpg" alt="" class="w-full h-[45%] object-cover" />
          <img src="/static/images/collage_bottom_right.jpg" alt="" class="w-full h-[33%] object-cover" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const open = ref('Pre-production')

const items = [
  {
    title: 'Pre-production',
    text: 'Проводим глубокий анализ вашего бренда, аудитории и конкурентов. Вместе с вами определяем ключевое сообщение и цели. Разрабатываем креативную концепцию и детальный план кампании.',
  },
  {
    title: 'Production',
    text: 'Создание фото/видео-ряда, разработка контент-плана, коллаборации с медиа и инфлюенсерами. Координируем все процессы для безупречного запуска.',
  },
  {
    title: 'Post-production',
    text: 'Мониторинг результатов, аналитика, отчётность. Корректируем стратегию по данным и закрепляем бренд в культурном контексте.',
  },
]

function toggle(title) {
  open.value = open.value === title ? null : title
}
</script>
