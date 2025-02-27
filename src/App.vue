<script setup lang="ts">
import bg from './assets/main.jpg';
import ym from './assets/bitmap.svg'
import './assets/main.css';
import Countdown from './components/Countdown.vue';
import PhoneButton from "@/components/PhoneButton.vue";
</script>

<template>
  <header class="w-full ma-0 p-0 position-relative bg-black">
    <div class="position-absolute buongiorno-rastellino text-h1 w-100 text-center"
         style="left: 50%; top: 50%; transform: translate(-50%, -50%); z-index: 3000">nuestro día especial
    </div>
    <v-img class="w-full ma-0 p-0 opacity-70" cover :src="bg"/>
  </header>

  <main class="d-flex flex-column justify-center align-center mt-10 ga-10 px-0">
    <div class="burgues text-h4 text-center" style="color: #504d4d">Acompáñanos</div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d"/>
    </div>
    <div class="px-6 text-center">
      Únete a nosotros para celebrar el comienzo de nuestra historia juntos. Será un día lleno
      de amor, alegría y
      momentos inolvidables.

      <div class="mt-0 pt-0">¡Esperamos contar contigo!</div>
      <div style="color: #504d4d">
        Yoel y Marta
      </div>
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d"/>
    </div>
    <div style="color: #504d4d">
      05 . 09 . 2025
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d"/>
    </div>
    <div class="d-flex flex-column align-center px-4 text-center" style="color: #504d4d">
      <v-icon icon="mdi-map-marker mb-3"/>
      <span>
        ALQUERÍA KUKALA - RESTAURANTE, BODAS Y EVENTOS
        S/N AVINGUDA DE LA MAR
        LA POBLA DE FARNALS, VC 46139
      </span>
      <a href="https://maps.app.goo.gl/XW3oJVjQ5kMKS73U6" class="ma-2 mt-4">
        <v-btn variant="outlined" color="black">
          Cómo llegar
        </v-btn>
      </a>
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d"/>
    </div>
    <div class="font-parfumerie text-h2" style="color: #504d4d">
      Programa
    </div>
    <div style="color: #504d4d">
      (Próximamente daremos detalles)
    </div>
    <v-progress-circular color="white" indeterminate></v-progress-circular>

    <v-divider color="#504d4d"/>
    <div class="text-center" style="color: #504d4d">

      Si tienes alguna necesidad alimentaria específica o precisas de menú infantil, no dudes en hacérnoslo saber.
      <br>
      ¡Queremos que todos disfrutéis del banquete!
    </div>

    <v-divider color="#504d4d"/>

    <Countdown class="my-3 w-100" targetDate="09/05/2025"/>

    <div style="color: #504d4d">
      ¿Quieres confirmar tu asistencia?
    </div>
    <div class="d-flex ga-2 mb-10" style="color: #504d4d">
      <PhoneButton :number="699480616" name="Y"/>
      <div class="mt-2">-</div>
      <PhoneButton :number="684098105" name="M" :icons-on-right="true"/>
    </div>
    <v-img class="mb-3 mt-16" :src="ym" width="30vw"/>
  </main>
</template>
<style>
main {
  color: #504d4d;
}
.font-parfumerie{
  font-family: 'Parfumerie', sans-serif;
}
</style>
