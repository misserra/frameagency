<template>
  <div class="bg-[#ede9e9] min-h-screen">
    <NavBar />
    <HeroSection />
    <AboutSection />
    <WhatWeDo />
    <HowWeWork />
    <FaqSection />
    <ContactForm />
    <FooterSection />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import WhatWeDo from './components/WhatWeDo.vue'
import HowWeWork from './components/HowWeWork.vue'
import FaqSection from './components/FaqSection.vue'
import ContactForm from './components/ContactForm.vue'
import FooterSection from './components/FooterSection.vue'
</script>
