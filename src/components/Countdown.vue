<script setup lang="ts">
import { ref, computed, onMounted, onBeforeUnmount } from 'vue';

// Define props with TypeScript
const props = defineProps<{
    targetDate: string;
}>();

// Reactive state for time remaining
const timeRemaining = ref(0);
let interval: number | null = null;

// Computed property to format the time
const formattedTime = computed(() => {
    const days = Math.floor(timeRemaining.value / (1000 * 60 * 60 * 24));
    const hours = Math.floor((timeRemaining.value % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((timeRemaining.value % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((timeRemaining.value % (1000 * 60)) / 1000);

    return `${days} : ${hours + 17} : ${minutes} : ${seconds}`;
});

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
    <v-card flat class="text-center pa-4">
        <v-card-text>
            <v-row justify="center">
                <v-col cols="auto">
                    <div class="text-h4">{{ formattedTime }}</div>
                    <div class="text-h6">DÍAS HORAS MINUTOS SEGUNDOS</div>
                </v-col>
            </v-row>
        </v-card-text>
    </v-card>
</template>