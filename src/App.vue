<script setup lang="ts">
import bg from './assets/main.jpg';
import ym from './assets/bitmap.svg'
import './assets/main.css';
import Countdown from './components/Countdown.vue';
</script>

<template>
  <header class="w-full ma-0 p-0 position-relative bg-black">
    <div class="position-absolute buongiorno-rastellino text-h1 w-100 text-center"
      style="left: 50%; top: 50%; transform: translate(-50%, -50%); z-index: 3000">nuestro día especial</div>
    <v-img class="w-full ma-0 p-0 opacity-70" cover :src="bg" />
  </header>

  <main class="d-flex flex-column justify-center align-center mt-10 ga-10 px-3">
    <div class="burgues text-h4 text-center" style="color: #504d4d">Acompáñanos</div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d" />
    </div>
    <div style="color: #504d4d">
      Únete a nosotros para celebrar el comienzo de nuestra historia juntos. Será un día lleno
      de amor, alegría y
      momentos inolvidables. ¡Esperamos contar contigo!
    </div>

    <div style="color: #504d4d">
      Yoel y Marta
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d" />
    </div>
    <div style="color: #504d4d">
      05 . 09 . 2025
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d" />
    </div>
    <div style="color: #504d4d">
      <v-icon icon="mdi-map-marker"></v-icon>
      ALQUERÍA KUKALA - RESTAURANTE, BODAS Y EVENTOS
      S/N AVINGUDA DE LA MAR
      LA POBLA DE FARNALS, VC 46139
      <v-btn variant="text">
        Cómo llegar
      </v-btn>
    </div>
    <div style="width: 15vw;">
      <v-divider color="#504d4d" />
    </div>
    <div style="color: #504d4d">
      programa
    </div>
    <div style="color: #504d4d">
      (Próximamente daremos detalles)
    </div>
    <v-progress-circular color="blue-lighten-3" indeterminate></v-progress-circular>

    <v-divider color="#504d4d" />
    <div style="color: #504d4d">

      Si tienes alguna necesidad alimentaria específica o precisas de menú infantil, no dudes en hacérnoslo saber.
      ¡Queremos que todos disfrutéis del banquete! </div>

    <v-divider color="#504d4d" />
    <Countdown targetDate="09/05/2025" />
    <div style="color: #504d4d">
      ¿Quieres confirmar tu asistencia?
    </div>
    <div class="d-flex" style="color: #504d4d">
      <div style="color: #504d4d">
        699480616 - <br>Y
      </div>
      <div style="color: #504d4d">
        684098105 <br>M
      </div>
    </div>
    <v-img :src="ym" width="30vw"/>
  </main>
</template>