<template>
  <div class="main">
    <h1>Dune Trivia</h1>
    <button @click="hideAll" class="flat-button">RESET</button>
    <div class="difficulty-options">
      <difficulty-options
        :difficulty="selectedDifficulty"
        @difficulty-change="handleDifficultyChange"
      />
    </div>
    <div class="cards">
      <div v-for="card in displayedTrivia" :key="card.id">
        <flash-card :card="card" @toggle="handleToggle" />
      </div>
    </div>
  </div>
</template>

<script>
import trivia from "../trivia";
import DifficultyOptions from "./DifficultyOptions.vue";
import FlashCard from "./FlashCard.vue";
export default {
  components: { FlashCard, DifficultyOptions },

  data() {
    return {
      trivia: [...trivia],
      selectedDifficulty: "all",
    };
  },

  methods: {
    handleToggle(card) {
      card.answerShown = !card.answerShown;
    },
    handleDifficultyChange(difficulty) {
      this.selectedDifficulty = difficulty;
    },
    hideAll() {
      this.trivia.forEach((t) => (t.answerShown = false));
    },
  },
  computed: {
    displayedTrivia() {
      if (this.selectedDifficulty === "all") {
        return this.trivia;
      }
      return this.trivia.filter(
        (t) => t.difficulty === this.selectedDifficulty
      );
    },
  },
};
</script>

<style scoped>
.cards {
    display: flex;
    flex-wrap: wrap;
    padding: 10px;
    justify-content: center;
}
</style>
