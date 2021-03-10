<template>
  <div :class="{ flipped: card.answerShown }">
    <h4>{{ card.question }}</h4>
    <div>
      <button @click="handleClick">See Answer</button>
    </div>
    <h4>{{ card.answer }}</h4>
  </div>
</template>

<script>
export default {
  props: ["card"],

  methods: {
    handleClick() {
      this.$emit("toggle", this.card);
    },
  },
};
</script>

<style>
.flipped  {
  transform: rotateY(180deg);
}
</style>
