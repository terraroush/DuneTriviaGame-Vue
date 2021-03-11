<template>
  <div id="app">
    <trivia-game />
  </div>
</template>

<script>
import TriviaGame from "./components/TriviaGame";
export default {
  name: "App",
  components: { TriviaGame },
};
</script>

<style>
body {
  background-image: linear-gradient(#6E352C, #6E352C, #F59A44, #E3C598, #8A6E64);
  height: 100vh;
  
}

</style>
