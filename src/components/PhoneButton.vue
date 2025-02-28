<script setup lang="ts">
import {useClipboard} from '@vueuse/core/index.cjs';
import {ref} from "vue";

defineProps({
  number: Number,
  name: String,
  iconsOnRight: Boolean
})
const {copy} = useClipboard()
const snackbar = ref(false)
</script>

<template>
  <div class="d-flex flex-column align-center ga-2 font-cmu font-weight-thin" style="color: #504d4d">
    <div class="d-flex align-top ga-2 ma-2 font-italic" :class="{'flex-row-reverse': iconsOnRight}">
      <v-icon icon="mdi-content-copy" class="me-1 mt-1"
              @click="copy(number!.toString()); snackbar = true"/>
      <a :href="`https://wa.me/34${number}`" style="color: green">
        <v-icon icon="mdi-whatsapp"></v-icon>
      </a>
      <div>
        {{ number }}
        <div class="text-center">{{ name }}</div>
      </div>
    </div>
  </div>
  <v-snackbar
    v-model="snackbar"
    color="black"
    :timeout="2000"
  >
    ¡Número copiado!

    <template v-slot:actions>
      <v-btn
        color="white"
        variant="text"
        @click="snackbar = false"
      >
        OK
      </v-btn>
    </template>
  </v-snackbar>
</template>

<style scoped>
.v-icon {
  font-size: 20px;
}
</style>
