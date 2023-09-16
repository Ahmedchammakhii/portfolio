<script setup lang="ts">
import { onMounted , ref,onUnmounted  } from 'vue';
import { gsap } from 'gsap';
const screens =  ["noise.gif","5i.gif","noise.gif","hulu.gif","noise.gif","afrahs.gif","noise.gif"]

const i = ref(0) ;
let interval = 0 ;
onMounted(()=>{
 interval = setInterval(() => {
    i.value = (i.value + 1) % screens.length;
  }, 1500);
  gsap.from(".greetings h1",{y:250,scale:.5,zIndex:-1,opacity:0,})
  gsap.from(".greetings h3",{y:250,scale:.5,delay:.5,zIndex:-1,opacity:0})

gsap.to(".greetings",{ rotate:"40%",scale:10,opacity:0,transformOrigin:"center 70%"
,scrollTrigger:{
    trigger:".tv_wrapper",
    start:"top top",
    scrub:true,
}})

})

onUnmounted (()=> clearInterval(interval))

const thescreen = ()=>{ 
  return '/assets/'+screens[i.value]}
</script>

<template>
    <header>
  <div class="greetings" >
    <h1>Chammakhi ahmad</h1>
    <h3 >FULL STACK DEVELOPER </h3>
    <div class="tv_wrapper" style="width: 100vw; height: 100vh;position: absolute;    background: url('/assets/back.webp') no-repeat ;
    background-position:center ;
    filter: brightness(200%) grayscale(40%);
   
    display: flex;
    justify-content: center;
    align-items: center;

 ">
 <div class="tv" style="width: 277px; height: 270px;  background: url('/assets/back.png') no-repeat ;
    background-position:center ;
    display: flex;
    justify-content: center;
    align-items: center;
    transform: translateY(202.8px) translateX(2.9px) scale(1.01);
     ">
  <img class="screen" :src="thescreen()"/> </div>
  </div>
  </div>
    </header>
</template>

<style scoped>

h1 {
    font-family: Valencia;
    font-size: calc(5.5rem + 2vw);
    font-weight: 200;
    text-align: center;
    z-index: 10;
    transform: translateY(-150px);
}
h3{
    font-family: sanshaa;   
    font-size: calc(1rem + .7vw);
    margin-bottom: 50px;
    padding-top: 0px;
    z-index: 10;
    transform: translateY(-150px);

}
.greetings {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
}

.tv_wrapper::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100px; 
  background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(255, 255, 255, 0.28)); 
  pointer-events: none; 
}


.screen {
 z-index: -1; height:180px;width: 250px;z-index: 1000;
 transition: background 1s ease-in-out;transform: translateY(-20px) translateX(2px);

}

</style>
