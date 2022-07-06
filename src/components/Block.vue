<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me!
  </div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactTime: 0
    };
  },
  mounted(){
    console.log('comp mounted');
    setTimeout(() => {
      this.showBlock= true
      this.startTimer();
      console.log(this.delay);
    }, this.delay);
  },
  updated(){
    console.log('comp updated');
  },
  unmounted(){
    console.log('comp unmounted');
  },
  methods: {
    startTimer(){
      this.timer = setInterval(()=>{
        this.reactTime += 10;
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer);
      this.$emit('end', this.reactTime)
    }
  }
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: rgb(121, 255, 215);
  padding: 100px 0;
  text-align: center;
  margin: 40px auto;
}
</style>