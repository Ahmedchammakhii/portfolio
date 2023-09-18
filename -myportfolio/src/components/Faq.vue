<script setup lang="ts">
import { onMounted,onBeforeMount, ref } from 'vue';
import gsap from "gsap"
const faq = ref([
  {number :"01." ,title:"HMED , HOW MUCH IS A WEBSITE",desc:"Hmm, let me ask you something first: How much is a car? Depends on which one you want, right? Same with websites: Costs depend on your requirements, scope and features. Therefore your budget defines what I can do for you. But don't worry, I am happy to tell you exactly what you will get for your budget once it is defined.",who:"Client",showed:false}
, {number :"02." ,title:"HMED , what web design trends can we expect soon ?",desc:"Old TVs on the streets will be the next big thing, according to trusted sources. Wallpaper patterns behind FAQs are also pretty hot right now. And rumor has it that every website needs at least one image of CHOUFLIHAL",who:"Client",showed:false}
,{number :"03.",title:"HMED , how do I become as awesome as you?",desc:"                " ,showed:false,who:"EVERYBODY"}
, {number :"04.",title:"HMED ,why don't you have any social media account",desc:"WELL YOU GOTTA WATCH TAXI DRIVER ASAP" ,showed:false,who:"NONE"}



])
const lastfaq = ref(false)

onMounted (()=> {

})


const show = (number : number)=> {
  console.log(number);
  
  if (number!==5)faq.value[number].showed = !faq.value[number].showed
else {lastfaq.value = !lastfaq.value ; 
  var audio = document.querySelector("#myAudio") as HTMLAudioElement;
  
  if (audio != null) audio.play()

}

}

</script>

<template>

<section class="faq">
<div class="bg__faq"></div>
<div class="sbou3i" >
</div>
<h1 style="padding-bottom: 100px;font-family: avenir;padding-left: 5% ;padding-top: 2%;">THEWALL.</h1>
<div class="all_faqs" v-for="(onefaq,i) of faq">
<div class="main_faq" @click="show(i)" >
<div class="onefaq" >
  <h1>{{ onefaq.number }}</h1>
<h1 class="qst">{{ onefaq.title }}</h1>
<h1 class="client">ASKED BY ({{ onefaq.who }})</h1>
</div>
<div class="resp" ><h2 v-if="onefaq.showed === true">{{onefaq.desc}}</h2></div>
</div>
</div>
<div class="all_faqs">
<div class="main_faq" @click="show(5)" style="border-bottom: 3px solid #fff;" >
<div class="onefaq">
  <h1>05.</h1>
<h1 class="qst">HMED , DONT FORGET THAT WE NEED TO FINISH STRONG , HUH</h1>
<h1 class="client">ASKED BY (you)</h1>
</div>
<div class="resp" v-if="lastfaq.valueOf() === true" >
<img id="mediaplayer" src="/assets/windows-media-player-10.jpg" alt="Windows player">
<h2 style="color: rgb(255, 255, 255);position: absolute;top:10%;width: 100%">A LIL BIT OF NOSTALGIAAA ? VOLUMEEE UP</h2>
<iframe src="//gifs.com/embed/windows-media-player-visualizations-oVrvEN" frameborder="0" scrolling="no" width="450px" height="360px" style="-webkit-backface-visibility: hidden;-webkit-transform: scale(.5);position: absolute;bottom: 10%;left: 5%;"></iframe>
</div>
</div></div>
<audio id="myAudio"  >
        <source src="/assets/mydream.mp3" >
    </audio>

</section>

</template>
<style scoped>
.all_faqs {
  padding-left: 5%;
}
.resp h2 {
  width: 50%;
  display: flex;
  text-align: center;
  padding: 50px;
}
.resp {
  display: flex;
}

.main_faq {
  width: 90%;
  height: max-content;
  padding: 20px;
  border-top: 2px solid rgb(255, 255, 255);
  position: relative;
overflow: hidden;
display: flex;
flex-direction: column;
justify-content: center;
transition: all ease 1s;
}
.onefaq {
  display: flex;
  gap: 10vw;
align-items: center;
z-index: 50000;
transition: all ease-in 1s;

}
.client {
  width: 50%;
  display: flex;
  justify-content: flex-end;
}

.main_faq::before {
  width: 120%;
  content: "";
  height: 100%;
  background: #000;
  position: absolute;
bottom: -100%;
transition: all ease 1s;
opacity: .2;
transition: all linear .5s;

}
.main_faq:hover::before {
bottom: 0;}
.main_faq:hover .onefaq h1:nth-child(1) {
transform: translateX(15px);}
.main_faq:hover .onefaq h1:nth-last-child(1) {
transform: translateX(-15px);}

.sbou3i { 
background: url("/assets/wallpic.png") no-repeat;
height: 400px;
width: 200px;
background-size:contain;
position: absolute;
left: 50%;
top: 10%;
z-index: -1;
transition: all ease-in 1s;
}
h1 {
  transition: all ease 1s;
}
.faq {
  margin-top: 50px;
  height: max-content;
  min-height: 110vh;
  width: 100vw;
position: relative;  
z-index: 10;
font-family: sanshaa;
background-color: #4750c9;
color: white;
transition: all linear 1s;

}
.faq > h1 {
  font-size: calc(3rem + 1vw);
}
.bg__faq {
  background: url("/assets/bg.jpg")  repeat ;
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  opacity: .5;
z-index: -1;
mix-blend-mode: darken;
}
.bg__faq::before {
  position: absolute;
  content: "";
  top: -10%;
  width: 100%;
  height: 100px; 
  background-image: linear-gradient(to top, rgba(255, 255, 255, 0), rgba(255, 255, 255, 1)); 
}
.bg__faq::after {
  position: absolute;
  content: "";
  bottom: 0;
  width: 100%;
  height: 100px; 
  background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(255, 255, 255, 1)); 
}

#mediaplayer {
transform: scale(.7);
}

@media screen and (max-width:650px) {
    h1 {
    position: relative;
    font-size: calc(.8rem + 1vw);

    }
.sbou3i {
  scale: .5;
  top: -4%;
  transform: translateX(-20%) !important ;
  opacity: .8;
}
     #mediaplayer {
transform: scale(.6) translateX(-30%)  !important;
}
#loadervideo {
    transform: scale(.2) translateY(110px) !important;

}
}
@media screen and (max-width:390px) {
#loadervideo {
    transform: scale(.2) translateY(200px) !important;

}
}
@media screen and (max-width:650px) {
     #mediaplayer {
transform: scale(.7) !important;
}
#loadervideo {
    transform: scale(.1) translateY(110px) !important;

}
}
audio::-webkit-media-controls-panel {
  display: none;
}
</style>

