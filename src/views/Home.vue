<script setup>
import { computed } from "vue";
import store from "../store";
const meals = computed(() => store.state.meals);
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
</script>

<template>
  <div class="flex justify-center p-8">
    <input
      type="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder=" search for meals"
    />
    <div class="flex gap-1">
      <router-link to="/" v-for="letter in letters.split('')">
        {{ letter }}
      </router-link>
    </div>
  </div>
</template>
