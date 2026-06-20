<template>
  <section class="relative h-screen min-h-175 overflow-hidden">
    <!-- Hero image -->
    <img
      src="/static/images/hero.jpg"
      alt="PR для создателей моды"
      class="absolute inset-0 w-full h-full object-cover object-bottom"
    />
    <!-- Gradient overlay -->
    <div class="absolute inset-0 bg-linear-to-r from-black/80 via-black/40 to-transparent"></div>

    <!-- Text -->
    <div class="relative z-10 flex flex-col justify-end h-full pb-20 pl-16">
      <h1 class="font-merriweather text-white leading-tight">
        <span class="block font-normal text-[clamp(2.5rem,6vw,4rem)]">PR для создателей</span>
        <span class="block font-light italic text-[clamp(2.5rem,6vw,4rem)]">моды</span>
      </h1>
    </div>
  </section>
</template>
