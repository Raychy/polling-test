<template>
  <main class="poll-container">
    <h2>{{ question }}</h2>
    <section v-if="!hasVoted" class="poll-choices">
      <button
        v-for="(choice, index) in choices"
        :key="index"
        @click="castVote(index)"
        class="choice-button"
      >
        <span class="checkmark" v-if="selectedIndex === index">✔</span>
        {{ choice.label }}
      </button>
    </section>
    <section v-else class="poll-results">
      <div
        v-for="(choice, index) in choices"
        :key="index"
        class="result"
        :class="{ selected: selectedIndex === index }"
      >
        <span class="label">{{ choice.label }}</span>
        <div class="progress-container">
          <div
            class="progress"
            :style="{ width: (choice.votes / totalVotes) * 100 + '%' }"
          ></div>
        </div>
        <span class="vote-count"
          >{{ ((choice.votes / totalVotes) * 100).toFixed(0) }}%</span
        >
      </div>
      <p class="total-votes">Total Votes: {{ totalVotes }}</p>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref } from "vue";

const question = ref("Which frontend framework do you prefer?");
const choices = ref([
  { label: "Vue", votes: 150 },
  { label: "React", votes: 80 },
  { label: "Angular", votes: 40 },
  { label: "Svelte", votes: 10 },
]);
const totalVotes = ref<number>(choices.value.reduce((sum, choice) => sum + choice.votes, 0));
const hasVoted = ref(false);
const selectedIndex = ref<number>();

// The function `castVote` enables user to cast vote as it accept the selected index
const castVote = (index: number) => {
  choices.value[index].votes++;
  totalVotes.value++;
  selectedIndex.value = index;
  hasVoted.value = true;
};
</script>
