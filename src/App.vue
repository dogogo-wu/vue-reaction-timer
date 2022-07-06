<template>
  <h1>Reaction Timer Game</h1>
  <button @click="start" :disabled="isPlay">Play</button>
  
  <Results v-if="showResult" :score="score" />
  <Block v-if="isPlay" :delay="delay" @end="endGame" />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlay: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.isPlay = true;
      this.delay = 2000 + Math.random()*5000;
      this.showResult = false;
    },
    endGame(reactTime){
      this.score = reactTime;
      this.showResult = true;
      this.isPlay = false;
    }
  },
};
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  button{
    background:#01b280;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 1rem;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 1rem;
  }
  button[disabled]{
    opacity: 0.2;
    cursor: not-allowed;
  }
</style>
