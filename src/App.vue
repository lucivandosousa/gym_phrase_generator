<template>
  <div class="bg-orange-300 m-auto h-screen p-10 flex flex-col items-center justify-center space-y-4">
    <h1 class="text-center text-2xl font-bold mb-4 text-gray-800">Receba sua motivação para malhar todos os dias.</h1>
    <PhraseGenerator />
  </div>
</template>

<script setup lang="ts">
import PhraseGenerator from "./components/phraseGenerator.vue";
</script>
