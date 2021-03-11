<template>
  <div>
    <button
      :class="{ active: difficulty === 'easy' }"
      @click="selectDifficulty('easy')"
    >
      easy
    </button>
    <button
      :class="{ active: difficulty === 'medium' }"
      @click="selectDifficulty('medium')"
    >
      medium
    </button>
    <button
      :class="{ active: difficulty === 'hard' }"
      @click="selectDifficulty('hard')"
    >
      hard
    </button>
    <button
      :class="{ active: difficulty === 'all' }"
      @click="selectDifficulty('all')"
    >
      all
    </button>
  </div>
</template>

<script>
export default {
  props: ["difficulty"],
  methods: {
    selectDifficulty(difficulty) {
      this.$emit("difficulty-change", difficulty);
    },
  },
};
</script>

<style scoped>
div {
  display: flex;
  justify-content: center;
}
button {
  background-color: #e2c7b6;
  box-shadow: 2px 2px black ;
  text-decoration: none;
  display: inline-block;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
  align-content: center;
  margin: 5px;
  padding: 5px;
}
button:hover {
  transform: scale(1.1);
  transition: 0.3s ease all;
}
</style>
