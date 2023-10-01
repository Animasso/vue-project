<script setup>
import { computed } from "vue";
import store from "../store";
const meals = computed(() => store.state.meals);
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
</script>

<template>
  <div class="flex flex-col items-center justify-center p-8">
    <input
      type="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder=" search for meals"
    />
    <div class="flex justify-center gap-1 p-4">
      <router-link
        :to="{ name: 'byLetter', params: { letter } }"
        v-for="letter in letters.split('')"
        :key="letter"
      >
        {{ letter }}
      </router-link>
    </div>
  </div>
</template>
