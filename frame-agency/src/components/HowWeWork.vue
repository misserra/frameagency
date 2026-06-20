<template>
  <section class="px-26 py-8">
    <h2 class="font-merriweather font-light text-[clamp(2rem,4vw,3.875rem)] text-center mb-16">Как мы работаем</h2>
    <div class=" grid grid-cols-[5fr_6fr] gap-16 items-center">
      <img
        src="/static/images/third_screen.jpg"
        alt=""
        class="relative bottom-5 w-100 h-130 object-cover "
      />
      <div>
        <div class="space-y-10">
          <div v-for="step in steps" :key="step.title" :class="step.width">
              <h3 class="font-merriweather font-light text-[clamp(2rem,3vw,2.8rem)] mb-2">{{ step.title }}</h3>
              <p class="font-inter font-normal text-[clamp(1rem,1.5vw,1.25rem)] tracking-wide text-neutral-600 leading-relaxed">{{ step.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const steps = [
  {
    title: 'Глубокий анализ',
    text: 'Анализ конкурентов, анализ целевой аудитории, разработка стратегии.',
    width: 'w-100',
  },
  {
    title: 'Запуск, отслеживание',
    text: 'Создание фото/видео-ряда, разработка контент-плана, коллаборации.',
    width: 'w-130',
  },
  {
    title: 'Медиа-присутствие',
    text: 'Работаем над интеграцией бренда в актуальную культурную и модную повестку, повышая его статус, авторитет и желательность.',
    width: 'w-140',
  },
]
</script>
