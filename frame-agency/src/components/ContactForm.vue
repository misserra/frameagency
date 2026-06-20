<template>
  <section id="contact" class="px-16 py-16">
    <h2 class="font-merriweather font-light text-[clamp(2rem,4vw,3.875rem)] text-center mt-18 mb-16">Давайте работать вместе</h2>

    <form class="max-w-lg mb-10 mx-auto space-y-0" @submit.prevent="submit">
      <input
        v-for="field in fields"
        :key="field.name"
        v-model="form[field.name]"
        :placeholder="field.label"
        :type="field.type || 'text'"
        class="w-full h-12 border border-black bg-transparent px-4 py-4 font-merriweather text-base placeholder-neutral-500 focus:outline-none focus:border-black -mt-px mb-4"
      />
      <p v-if="error.isError" class="text-center mt-4 font-inter text-sm text-red-600">{{ error.message }}</p>
      <button
        type="submit"
        class="w-full bg-black text-white font-inter font-medium text-sm tracking-[0.12em] uppercase py-4 hover:bg-neutral-800 transition-colors -mt-px"
      >
        Отправить
      </button>
    </form>

    <p v-if="sent" class="text-center mt-6 font-inter text-sm tracking-wide text-neutral-600">
      Спасибо! Мы свяжемся с вами в ближайшее время.
    </p>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

import emailjs from '@emailjs/browser'

const sent = ref(false)
const loading = ref(false)
const error = ref({isError: false, message: ''})

const form = reactive({ name: '', phone: '', email: '', project: '', company: '', contact: '' })

const fields = [
  { name: 'name', label: 'Имя' },
  { name: 'phone', label: 'Телефон' },
  { name: 'email', label: 'E-mail', type: 'email' },
  { name: 'project', label: 'Расскажите о проекте или отправьте резюме' },
  { name: 'company', label: 'Ваша компания' },
  { name: 'contact', label: 'Как с вами лучше связаться?' },
]

async function submit() {
  loading.value = true
  error.value = { isError: false, message: '' }
  try {
    await emailjs.send(
      'service_yajfm2q',
      'template_kzt3esb',
      {
        name: form.name,
        phone: form.phone,
        email: form.email,
        project: form.project,
        company: form.company,
        contact: form.contact,
      },
      'L4wgGeltt64QVvu2g'
    )
    sent.value = true
  } catch (e) {
    error.value = { isError: true, message: 'Произошла ошибка при отправке формы. Пожалуйста, попробуйте еще раз.' + `\n ${e.message}`  }
  } finally {
    loading.value = false
  }
}
</script>
