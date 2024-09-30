<template>
  <div class="div1">hey</div>
  <div class="div2">
      <div class="square"></div>
      <div class="square2"></div>
  </div>
</template>

<script lang="ts" setup>
// Import necessary modules
import { onMounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

// Register the ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger);

// Use onMounted lifecycle hook to ensure the DOM is ready
onMounted(() => {
  // Apply GSAP animations after the component is mounted
  gsap.to(".square", {
    // x: 700,       // Move the square horizontally by 700px
    duration: 3,  // Animation duration of 3 seconds
    scrollTrigger: {
      trigger:".square2",
      start:"top 80%",
      end:"top 30%",
      scrub: 4,
      pin:".square",
      pinSpacing: true,
      toggleActions:"play none none none",
      // toggleClass:"red",
      markers:{
        startColor:"purple",
        endColor:"fuchisa",
        fontSize:"3rem",
      },

    },
    // ease: "power1.out",
    // yoyo:true,
    // repeat:-1,
  });
});
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
.square2{
  margin-top: 300px;
  width: 150px;
  height: 150px;
  background: blue;
}
.red{
  background-color: brown;
}
</style>