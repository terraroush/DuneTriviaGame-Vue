<template>
  <div class="card" :class="{ flipped: card.answerShown }">
    <div class="card-inner">
      <div class="question">
        <h4 :class="{ hidden: card.answerShown }">{{ card.question }}</h4>
      </div>
      <div class="answer">
        <h4 :class="{ hidden: !card.answerShown }">{{ card.answer }}</h4>
      </div>
      <div>
        <button @click="handleClick">
          <img src="../../src/assets/rightbutton.png" />
        </button>
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

<style scoped>
.card {
  border-radius: 10px;
  height: 200px;
  width: 300px;
  border: 1px solid black;
  background-color: #88805c;
  padding: 10px;
  align-content: center;
  text-align: center;
  perspective: 1000px;
  margin: 20px;
  box-shadow: 2px 2px black ;
}
.card:hover {
  transform: scale(1.1);
  transition: 0.3s ease all;
}
.card-inner {
  position: absolute;
  height: 90%;
  width: 90%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}
.flipped .card-inner {
  transform: rotateY(180deg);
}

.answer {
  transform: rotateY(180deg);
}
.hidden {
  display: none;
}

button {
  position: relative;
  text-decoration: none;
  display: inline-block;
  border: none;
  cursor: pointer;
  background-color: transparent;

  -webkit-appearance: none;
  -moz-appearance: none;
}
button:hover,
button:focus {
  position: inherit;
  transform: scale(1.5);
  transition: 0.3s ease all;
}
img:hover {
  transform: translate(8px);
  transition: 0.3s ease all;
}

button:focus {
  outline: none;
}

button:active {
  transform: scale(0.99);
}
</style>
