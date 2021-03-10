<template>
<div>
    <h1>Dune Trivia</h1>
    <div v-for="card in trivia" :key="card.id">
        <flash-card :card="card" />
    </div>
</div>
</template>

<script>
import trivia from "../trivia";
import FlashCard from './FlashCard.vue';
export default {
    components: {FlashCard},
    data() {
        return {
            trivia: [...trivia],
        }
    }

}
</script>

<style>

</style>