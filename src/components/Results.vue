<template>
  <p>Your Reaction Time is: {{ score }} ms</p>
  <div class="rank">{{ rank }}</div>
</template>

<script>
    export default {
    props: ["score"],
    data() {
        return {
        rank: null,
        };
    },
    mounted() {
        if (this.score <= 300) {
        this.rank = "Very Fast !!!";
        } else if (this.score <= 500) {
        this.rank = "Fast enough !";
        } else {
        this.rank = "Kind of slow...";
        }
    },
    };
</script>

<style>
    .rank{
        font-size: 1.4rem;
        color: #01b280;
        font-weight: bold;
    }
</style>