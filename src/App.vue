<script setup lang="ts">
import bg from './assets/main.jpg';
import ym from './assets/bitmap.svg'
import './assets/main.css';
import Countdown from './components/Countdown.vue';
import PhoneButton from "@/components/PhoneButton.vue";
import meme from './assets/meme.mp3'
import cake from './assets/cake.svg'
import disco from './assets/disco.svg'
import rings from './assets/rings.svg'
import cocktail from './assets/cocktail.svg'
import { ref } from "vue";

const audio = ref(new Audio(meme))
const hasPlayed = ref(!window.location.search.includes('ivanesgay'));
const isZoom = ref(window.location.href.includes('zoom'));
const layerVisible = ref(true);
window.addEventListener('scroll', () => {
  if (!hasPlayed.value) {
    audio.value.play();
    hasPlayed.value = true;
  }
})
</script>

<template>
  <Transition name="fade" mode="out-in">
    <div class="w-100 h-100 bg-black" v-if="layerVisible">
      <div class="position-relative">
        <v-img class="w-full ma-0 p-0 opacity-40 font-beautifully " position="top" style="filter: blur(4px)" cover
          height="100vh" :src="bg" />
        <v-btn class="position-absolute" variant="outlined" color="white"
          style="top:50%; left: 50%; transform: translate(-50%,-50%)" @click="layerVisible = false">Descubre
          nuestra boda
        </v-btn>
      </div>
    </div>
    <div class="w-100 h-100" v-else>
      <header class="w-full ma-0 p-0 position-relative bg-black">
        <div class="position-absolute font-buongiorno w-100 text-center title-25"
          style="left: 50%; top: 50%; transform: translate(-50%, -50%); z-index: 3000">nuestro día especial
        </div>
        <v-img class="ma-0 p-0 opacity-70" height="70vh" lazy-src="" position="top" width="100%" cover :src="bg" />
      </header>

      <main class="d-flex flex-column justify-center align-center mt-10 ga-10 px-0">
        <div class="font-parfumerie text-center title-18">Acompáñanos</div>
        <div style="width: 15vw;">
          <v-divider :thickness="2" />
        </div>
        <div class="px-6 text-center font-newstandard">
          <div class="py-4" v-if="!isZoom">
            Únete a nosotros para celebrar el comienzo de nuestra historia juntos. Será un día lleno
            de amor, alegría y
            momentos inolvidables.
          </div>
          <div class="py-4" v-else>
            Únete a nosotros, desde donde estés, para
            celebrar el comienzo de nuestra historia
            juntos.

            Aunque no podamos vernos en persona, nos
            hace mucha ilusión compartir este
            momento con todos vosotros.

            Conéctate por Zoom y acompáñanos en este
            día tan especial.
          </div>

          <div class="mt-0 pt-0">¡Esperamos contar contigo!</div>
          <div class="font-beautifully text-h4 pt-2">
            Yoel y Marta
          </div>
        </div>
        <div v-if="!isZoom" style="width: 15vw;">
          <v-divider :thickness="2" />
        </div>
        <div class="font-literaturnaya d-flex w-100 px-13 text-h5" style="max-width: 600px">
          05
          <v-spacer class="flex-grow-1" />
          .
          <v-spacer class="flex-grow-1" />
          09
          <v-spacer class="flex-grow-1" />
          .
          <v-spacer class="flex-grow-1" />
          25
        </div>
        <div v-if="!isZoom" style="width: 15vw;">
          <v-divider />
        </div>
        <div v-if="!isZoom" class="d-flex flex-column align-center px-4 text-center font-cmu " style="font-size: small">
          <v-icon icon="mdi-map-marker mb-3" />
          <span>
            ALQUERÍA KUKALA - RESTAURANTE, BODAS Y EVENTOS
            S/N AVINGUDA DE LA MAR
            LA POBLA DE FARNALS, VC 46139
          </span>
          <a href="https://maps.app.goo.gl/XW3oJVjQ5kMKS73U6" class="ma-2 mt-4">
            <v-btn variant="outlined" color="black" density="compact">
              Cómo llegar
            </v-btn>
          </a>
        </div>
        <div v-else class="d-flex flex-column align-center px-4 text-center font-cmu mt-8 " style="font-size: small">
          <a href="https://us06web.zoom.us/j/86729065312?pwd=SV9miLfDGTSO9zavhGo6d5d6Vsfa1K.1" class="font-parfumerie text-center text-h4 font-weight-bold text-grey-darken-4 text-decoration-none">- Enlace directo Ceremonia -</a>

          <p class="text-subtitle-1 mb-4  font-newstandard"><strong>↑</strong> Pincha aqui <strong>↑</strong></p>

          <p class="text-h6 font-newstandard">ID de reunión: 867 2906 5312</p>

          <p class="text-h6 mb-15 font-newstandard">Código de acceso: 050925</p>
        </div>
        <div style="width: 15vw;">
          <v-divider :thickness="2" />
        </div>
        <div v-if="!isZoom" class="font-parfumerie text-h2" style="color: #504d4d">
          Programa
        </div>
        <div v-if="!isZoom" class="d-flex flex-column ga-6  icon-images font-cmu">
          <div class="d-flex w-100 ga-4 align-center justify-start text-grey-darken-2">
            <v-img :aspect-ratio="1" contain height="28px" width="28px" :src="rings" />
            <span>19:30 Ceremonia</span>
          </div>
          <div class="d-flex w-100 ga-4 align-center">
            <v-img :aspect-ratio="1" contain height="28px" width="28px" :src="cocktail" />
            <span>20:15 Cóctel</span>
          </div>
          <div class="d-flex  w-100 ga-4 align-center">
            <v-img :aspect-ratio="1" contain height="28px" width="28px" :src="cake" />
            <span>21:00 Banquete</span>
          </div>
          <div class="d-flex w-100 ga-4 align-center">
            <v-img :aspect-ratio="1" contain height="28px" width="28px" :src="disco" />
            <span>23:30 Baile</span>
          </div>
        </div>
        <div v-if="isZoom" class="px-4 text-center font-cmu mt-8 text-body-1  font-newstandard">
          Importante:<br></br>

          Para acceder a la ceremonia por Zoom, es
          necesario conectarse con nombre y apellido
          reales, ya que solo se dará acceso a personas
          identificadas.
          <br></br>
          <br></br>
          Os pedimos también que no compartáis el
          enlace con nadie que no haya sido invitado
          directamente por nosotros.
          <br></br>
          Este momento es muy especial y queremos
          compartirlo únicamente con quienes forman
          parte de nuestra historia.
          <br></br><br></br>


          ¡Gracias de corazón por acompañarnos!
        </div>

        <v-divider v-if="!isZoom" :thickness="2" />
        <div v-if="!isZoom" class="px-4 text-center font-newstandard" style="color: #504d4d">

          Si tienes alguna necesidad alimentaria específica o precisas de menú infantil, no dudes en hacérnoslo saber.
          <br>
          ¡Queremos que todos disfrutéis del banquete!
        </div>

        <v-divider :thickness="2" />

        <Countdown class="my-3 w-100" targetDate="2025-09-05T17:00:00.000Z" />

        <div v-if="!isZoom" class="font-beautifully text-h4 text-no-wrap font-weight-bold">
          ¿Quieres confirmar tu asistencia?
        </div>
        <div v-else class="font-beautifully text-h4 text-no-wrap font-weight-bold">
          ¿Tienes alguna duda?
        </div>
        <div class="d-flex ga-2 mb-8" style="color: #504d4d">
          <PhoneButton :number="699480616" name="Y" />
          <div class="mt-2">-</div>
          <PhoneButton :number="684098105" name="M" :icons-on-right="true" />
        </div>
        <v-img class="mb-3 mt-8" :src="ym" width="30vw" />
      </main>
    </div>
  </Transition>
  <Transition>

  </Transition>
</template>
<style>
main {
  color: #504d4d;
  font-size: large;
}

.title-25 {
  font-size: 25vw;
}

.title-18 {
  font-size: 18vw;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
