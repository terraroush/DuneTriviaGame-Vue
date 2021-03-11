<template>
  <div class="main">
    <h1>Dune Trivia</h1>
    <button @click="reset" class="flat-button">RESET</button>
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
    reset() {
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
h1 {
    font-size: 50px;
    align-self: center;
}
button {
    width: 100px;
    align-self: center;
    background-color: #E2C7B6;
    text-decoration: none;
    display: inline-block;
    border: none;       
    cursor: pointer;
    border-radius: 5px;
    text-align: center;
    align-content: center;
    margin: 5px;
    padding: 5px;
    box-shadow: 2px 2px black ;
}
button:hover {
  transform: scale(1.1);
  transition: 0.3s ease all;
}
.main {
    display: flex;
    flex-direction: column;
  overflow: auto;
  max-height: 93vh;
}
.cards {
  display: flex;
  flex-wrap: wrap;
  padding: 10px;
  justify-content: center;
}
</style>
