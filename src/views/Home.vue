<template>
  <div class="home">
    <h1 class="text-6xl">Dad jokes API</h1>
    <div v-if="dadJokes.loading">Loading...</div>
    <div v-if="!dadJokes.loading && dadJokes.error">{{ dadJokes.error }}</div>
    <div v-if="dadJokes.data !== null">{{ dadJokes.data.joke }}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import useFetch from "@/hooks/useFetch";

export default defineComponent({
  setup() {
    interface DadJokesResponse {
      id: string;
      joke: string;
      status: number;
    }
    const dadJokes = useFetch<DadJokesResponse>("https://icanhazdadjoke.com/");

    return {
      dadJokes,
    };
  },
});
</script>
