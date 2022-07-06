<template>
  <h1>Reaction Timer Game</h1>
  <button @click="start" :disabled="isPlay">Play</button>
  <Block v-if="isPlay" :delay="delay" />
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: "App",
  components: { Block },
  data() {
    return {
      isPlay: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.isPlay = true;
      this.delay = 2000 + Math.random()*5000;
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
</style>
