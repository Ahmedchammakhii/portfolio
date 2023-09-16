<script setup lang="ts">
import { onMounted, ref } from 'vue';
import ScrollTrigger from "gsap/ScrollTrigger";
import gsap from "gsap"
gsap.registerPlugin(ScrollTrigger);

const about = ref("Crafting user friendly and aesthetic websites is not just a profession for me , it's my passion")
onMounted(() => {
    if (window.innerWidth >= 600) {
    gsap.to("#transition", {
    x: '35%',
    scrollTrigger: {
      trigger: "#main_container",
      start: "top top",
      end: () => {
        const mainContainer = document.querySelector("#main_container");
        if (mainContainer instanceof HTMLElement) {
    return `+=${mainContainer.offsetHeight /2 }`  }
else {return "bottom bottom"}},
      scrub: true,
      pin: true, 
    }
  });
}
});
</script>

<template>
<article id="main_container">
<div class="left">
</div>
<p id="transition">ABOUT ME</p>

<div class="right">
<p >{{about}}</p>
</div>
</article>
</template>

<style scoped>
article {
    width: 100vw;
    height: 100vh;
    display: flex;
    position: relative;

}
.left {
    width: 35%;

}
p{
    font-family: avenir;   
    font-size: calc(5rem + 5vw);
    position: absolute;
  
    opacity: .1;

}
#transition {
    left: 5%;
}
.right {
    padding-top: 100px;
}
.right p {
    font-family: sanshaa;   
    font-size: calc(1rem + .7vw);
    opacity: 1;
text-align: center;
width: 60%;
}
@media screen and (max-width: 600px) {
    .main_container{
        scale: .9;
    }
}
</style>