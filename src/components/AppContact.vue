<template>
  <section class="section">
    <h2>Contactarme</h2>
    <div class="contact-info">
      <div class="contact-item">
        <i class="fas fa-envelope"></i>
        <p>santarenaagustin69@gmail.com</p>
      </div>
      <div class="contact-item">
        <i class="fas fa-phone"></i>
        <p>+54 260 4390104</p>
      </div>
      <div class="contact-item">
        <i class="fab fa-github"></i>
        <p>github.com/AgusSantarena</p>
      </div>
    </div>
    <form class="contact-form" @submit.prevent="handleSubmit">
      <input type="text" placeholder="Nombre" required v-model="name">
      <input type="email" placeholder="Email" required v-model="email">
      <textarea placeholder="Mensaje" required v-model="message"></textarea>
      <button type="submit">Enviar Mensaje</button>
    </form>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const name = ref('');
const email = ref('');
const message = ref('');

const handleSubmit = () => {
  alert('Mensaje enviado (simulado).'); // Simulación por ahora
  name.value = '';
  email.value = '';
  message.value = '';
};
</script>