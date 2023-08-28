<template>
  <div class="wrapper">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 80 80" width="180" height="180"  preserveAspectRatio="xMinYMin meetv" version="1.1"
      class="svg">
      <circle id="sun" cx="40" cy="40" r="10" stroke="gray" stroke-width="1" fill="gray" />
      <circle id="earthPath" cx="40" cy="40" r="20" stroke="gray" stroke-width="1" fill="none" />
      <circle id="satelite" cx="24" cy="50" r="4" fill="gray" />

    </svg>
    <h4>
      This DEMO is built for The TV Series <a href="https://www.syfy.com/the-expanse/">
        《THE EXPANSE》
      </a>
    </h4>
    <p style="width: 50%">
      Because of the love for 《THE Expanse》,I Buit this page want to use some animation to reproduct a universe map or something
    </p>
    <p style="width: 50%">
      Wait for a few time
    </p>
    <p style="width: 50%">
      一个关于太空/宇宙的DEMO，由浩瀚苍穹，星穹铁道，星际公民启发，想要实现一个关于宇宙的动画demo。
      目前尚待实现
    </p>
    <p class="logo-info">
      <a href="https://greensock.com" target="_blank"><img class="gsap-3-logo" src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/gsap-3-logo.svg" width="110" /></a>
      <img class="gsap-3-logo" style="position: relative;" src="./assets/syfy.svg" width="110" />
    </p>
  </div>
</template>

<script  setup>
import gsap from "gsap";
import { MotionPathPlugin } from 'gsap/MotionPathPlugin'
import { ref, onMounted } from 'vue'
gsap.registerPlugin(MotionPathPlugin)

onMounted(() => {
  MotionPathPlugin.convertToPath("#earthPath");
  gsap.to('#satelite', {
    motionPath: {
      path: "#earthPath",
      align: "#earthPath",
      alignOrigin: [0.5, 0.5],


    },
    duration: 20,
    repeat: -1,
    ease: 'none'

  })
})
</script>

<style scoped>
.box {
  background: rgb(16, 85, 235);
  width: 20px;
  height: 20px;

  margin-top: 4px;
  border-radius: 20px;
}
.wrapper{
  position: relative;
  text-align: center;
  background: rgb(247, 245, 245);
  width: 80%;
  height: 800px;
  margin: 60px auto;
  
}
.wrapper p{
 margin: 0 auto;
}
.logo-info{
display: flex;
justify-content: center;
margin-top: 200px !important;
}
.logo-info img{
  margin-right: 20px;
}

</style>