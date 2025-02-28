<script setup lang="ts">
import {ref, computed, onMounted, onBeforeUnmount} from 'vue';
import image from "@/assets/main.jpg"
// Define props with TypeScript
const props = defineProps<{
  targetDate: string;
}>();

// Reactive state for time remaining
const timeRemaining = ref(0);
let interval: number | null = null;

// Computed property to format the time
const days = computed(() => Math.floor(timeRemaining.value / (1000 * 60 * 60 * 24)))
const hours = computed(() => Math.floor((timeRemaining.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)))
const minutes = computed(() => Math.floor((timeRemaining.value % (1000 * 60 * 60)) / (1000 * 60)))
const seconds = computed(() => Math.floor((timeRemaining.value % (1000 * 60)) / 1000))

// Function to update the countdown
const updateCountdown = () => {
  const now = new Date().getTime();
  const target = new Date(props.targetDate).getTime();
  timeRemaining.value = target - now;

  if (timeRemaining.value < 0) {
    timeRemaining.value = 0;
    if (interval) clearInterval(interval);
  }
};

// Start the countdown when the component mounts
onMounted(() => {
  updateCountdown();
  interval = setInterval(updateCountdown, 1000);
});

// Cleanup the interval when the component is destroyed
onBeforeUnmount(() => {
  if (interval) clearInterval(interval);
});
</script>

<template>
  <div class="text-center position-relative d-flex align-center justify-center" style="height: 80vh;background-color: white">
    <v-card-text>
      <v-row justify="center">
        <v-col cols="auto w-100">
          <div class="text-h4 font-weight-bold d-flex ga-2 justify-center">
            <div>
              {{ days }}
              <div style="font-size: 10px">DÍAS</div>
            </div>
            <span>:</span>
            <div>
              {{ hours }}
              <div style="font-size: 10px">HORAS</div>
            </div>
            <span>:</span>
            <div>
              {{ minutes }}
              <div style="font-size: 10px">MINUTOS</div>

            </div>
            <span>:</span>
            <div>
              {{ seconds }}
              <div style="font-size: 10px">SEGUNDOS</div>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-card-text>

    <v-img class="position-absolute" height="80vh" position="top " width="auto" cover :src="image" alt=""
           style="top:0; opacity: 0.2; filter:blur(5px);"/>
  </div>
</template>
<style scoped>

</style>
