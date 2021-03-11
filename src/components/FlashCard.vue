<template>
  <div class="card" :class="{ flipped: card.answerShown }">
    <div class="card-inner">
      <div class="question">
        <h4>{{ card.question }}</h4>
      </div>
      <div>
        <button @click="handleClick">See Answer</button>
      </div>
      <div class="answer">
        <h4>{{ card.answer }}</h4>
      </div>
    </div>
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
.flipped {
  transform: rotateY(180deg);
}
.card {
    height: 200px;
    width: 300px;
    /* border: 1px solid black; */
    padding: 10px;
    align-content: center;
    text-align: center;
}
.card-inner {
    border: 1px solid black;
    height: 200px;
    width: 300px;
    padding: 5px;
}
</style>
