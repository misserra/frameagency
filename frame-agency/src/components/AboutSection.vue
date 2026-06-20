<template>
  <section id="about" class="px-32 py-8 grid grid-cols-[1fr_1fr] gap-16 items-center">
    <div class="relative z-10 bg-transparent pt-0 pr-0 py-12 -mr-48 self-start">
      <p class="font-merriweather font-light text-[clamp(1.6rem,3.8vw,3rem)] leading-[1.1]">
        Frame — PR-агентство, работающее с модой, как с культурным высказыванием.
      </p>
      <ul class="mt-10 space-y-2">
        <li v-for="item in services" :key="item" class="font-inter font-light text-[clamp(1.2rem,2.5vw,1.5rem)] tracking-wide text-neutral-700">
          — {{ item }}
        </li>
      </ul>
    </div>
    <div class="relative h-125 -ml-14">
      <img
        src="/static/images/right_large.jpg"
        alt=""
        class="absolute inset-0 w-full h-full object-cover pl-48"
      />
      <img
        src="/static/images/left_small.jpg"
        alt=""
        class="absolute bottom-20 left-0 w-80 object-cover shadow-xl"
      />
    </div>
  </section>
</template>

<script setup>
const services = [
  'Запуски коллекций',
  'Стратегия продвижения',
  'Повышение узнаваемости',
  'Долгосрочный бренд-имидж',
]
</script>
