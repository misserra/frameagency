<template>
  <section class="px-16 py-6">
    <h2 class="font-merriweather font-light text-[clamp(2rem,4vw,3.875rem)] text-center mb-6">Часто задаваемые вопросы</h2>

    <div class="max-w-4xl mx-auto bg-[#ede9e9] rounded-[20px] px-10 space-y-2">
      <div v-for="(item, i) in faqs" :key="i">
        <button
          class="w-full flex items-center gap-6 py-5 text-left group"
          @click="toggle(i)"
        >
          <span class="font-merriweather font-light text-5xl text-neutral-400 w-16 shrink-0">
            {{ String(i + 1).padStart(2, '0') }}
          </span>
          <span class="font-inter font-light text-xl flex-1 leading-snug group-hover:opacity-70 transition-opacity">
            {{ item.q }}
          </span>
          <span class="text-2xl font-light text-neutral-500 shrink-0 transition-transform duration-300" :class="{ 'rotate-45': open === i }">
            +
          </span>
        </button>
        <div
          v-show="open === i"
          class="pl-22 pb-5 font-inter font-light text-base leading-relaxed text-neutral-700"
        >
          {{ item.a }}
        </div>
        <hr class="border-black/15" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const open = ref(0)

const faqs = [
  {
    q: 'Что входит в этап анализа и стратегии?',
    a: 'Мы изучаем ваш текущий бренд, целевую аудиторию и конкурентов. Проводим аудит соцсетей и позиционирования. Затем вместе определяем цели и ключевое сообщение, разрабатываем креативную концепцию и детальный план кампании: визуальный стиль, контент-план, каналы продвижения и KPI.',
  },
  {
    q: 'Какой бюджет необходим для запуска?',
    a: 'Бюджет формируется индивидуально под каждый проект. На первичном звонке мы обсуждаем ваши задачи и предлагаем оптимальный пакет. Напишите нам — расскажем подробнее.',
  },
  {
    q: 'Когда я увижу первые результаты?',
    a: 'Первые измеримые результаты обычно видны через 4–6 недель после старта кампании. Всё зависит от выбранных каналов и масштаба работ.',
  },
  {
    q: 'Вы работаете только с определённым стилем?',
    a: 'Нет. Мы работаем с самыми разными направлениями в моде — от streetwear до haute couture. Главное для нас — искренность бренда и его культурная релевантность.',
  },
]

function toggle(i) {
  open.value = open.value === i ? null : i
}
</script>
