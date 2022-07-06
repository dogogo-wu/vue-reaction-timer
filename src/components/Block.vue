<template>

  <div class="block">Click me!</div>

</template>

<script>

export default {
    props:['delay']
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