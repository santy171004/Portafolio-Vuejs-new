<template>
  <div id="app">
    <AppHeader />
    <main>
      <div class="bloques-container">
        <AppAbout id="sobremi" class="bloque reveal" />
        <AppStudies id="estudios" class="bloque reveal" />
      </div>
      <div class="bloques-container">
        <AppProjects id="proyectos" class="bloque reveal" />
        <AppContact id="contacto" class="bloque reveal" />
      </div>
    </main>
    <AppFooter />
  </div>
</template>

<script setup>
import AppHeader from './components/AppHeader.vue';
import AppAbout from './components/AppAbout.vue';
import AppStudies from './components/AppStudies.vue';
import AppProjects from './components/AppProjects.vue';
import AppContact from './components/AppContact.vue';
import AppFooter from './components/AppFooter.vue';
import { onMounted } from 'vue';

onMounted(() => {
  function revealSections() {
    const reveals = document.querySelectorAll(".reveal");
    for (let i = 0; i < reveals.length; i++) {
      const windowHeight = window.innerHeight;
      const elementTop = reveals[i].getBoundingClientRect().top;
      const revealPoint = 100;

      if (elementTop < windowHeight - revealPoint) {
        reveals[i].classList.add("active");
      }
    }
  }

  document.title = 'Santiago Martin - Portafolio';

  window.addEventListener("scroll", revealSections);
  revealSections();
});
</script>

<style>
</style>