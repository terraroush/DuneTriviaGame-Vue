<template>
<div>
    <h1>Dune Trivia</h1>
    <div v-for="card in trivia" :key="card.id">
        <flash-card :card="card" @toggle="handleToggle" />
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
    },

    methods: {
        handleToggle(card) {
            card.answerShown = !card.answerShown
        }
    }

}
</script>

<style>

</style>