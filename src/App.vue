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
  margin: 0 auto;
  padding: 0;
  background-image: linear-gradient(
    
    #744841,
    #D58A64,
    #EBE1D3,
    #BC8D81
  );
  height: 100vh;
  font-family: 'Gruppo', cursive;
  font-size: 20px;
}
body::-webkit-scrollbar {
  display: none;
}
</style>
