<template>
  <div class="div1">hey</div>
  <div class="div2">
      <div class="square"></div>
  </div>
</template>

<script lang="ts" setup>
// Import necessary modules
import { onMounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

// Register the ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger);



</script>

<style scoped>
.div1, .div2{
  height: 100vh;
}
.div1{
  background-color: pink;
}
.div2{
  background-color: salmon;
}
.square{
  width: 150px;
  height: 150px;
  background: fuchsia;
}
</style>