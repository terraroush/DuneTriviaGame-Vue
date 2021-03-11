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

<style></style>
