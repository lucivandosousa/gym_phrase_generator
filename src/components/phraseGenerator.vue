<template>
  <div class="flex flex-col items-center justify-center min-h-52 p-4 gap-12 bg-[#D5DADB] rounded-lg shadow-2xl shadow-slate-700">
    <div class="h-full">
      <p
        v-if="phraseOfDay"
        class="text-center text-2xl font-bold mb-4 text-gray-800"
      >
        "{{ phraseOfDay.phrase }}"
      </p>
      <p
        v-else
        class="text-center text-2xl font-bold mb-4 text-gray-800"
      >
        Clique no botão abaixo para gerar sua frase do dia.
      </p>
    </div>
    <button
      @click="randomIndex"
      class="bg-[#9D7166] text-gray-200 font-bold py-3 px-6 rounded transition-all duration-200 shadow-lg hover:scale-105"
      aria-label="Gerar uma nova frase do dia"
    >
      Gerar nova frase
    </button>
  </div>
</template>

<script setup lang="ts">
import { data } from "../utils/phrases.ts";
import { ref } from "vue";

interface PhraseOfDayProps {
  id: number;
  phrase: string;
}

const phraseOfDay = ref<PhraseOfDayProps | null>(null);

const randomIndex = () => {
  const index = Math.floor(Math.random() * data.length + 1);
  phraseOfDay.value = data[index];
}

</script>
