<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Aboutme from './components/Aboutme.vue';
import Header from './components/Header.vue'
import Oneproject from './components/Oneproject.vue';
import Skills from "./components/Skills.vue"
import  ContactVue from './components/Contact.vue';
import Faq from './components/Faq.vue';
import gsap from 'gsap';
const projects=ref([{number:'01', name:"VAWZEN", description:" PORTFILO FOR A DIGITAL COMPANY MADE WITHIN 2 DAYS",link:"https://vawzen.org/"}
, {number:'02', name:"5I", description:" SUPER-IINTERACTIVE WEBSITE BUILT FOR A BRANDING AGENCY",link:"https://5i.vercel.app/"}
,{number:'03', name:"AFRAH", description:" WEBSITE BUILT FOR A WEDDING PLANNER USING NEXTJS",link:"https://afrah-eta.vercel.app/"}
,{number:'04', name:"E-TAFAKNA", description:"I PLAYED A PIVOTAL ROLE AS A TECH LEAD IN THE DEVELOPMENT OF TWO CUTTING-EDGE APPLICATIONS AND A ROBUST PLATFORM. ",link:"https://e-tafakna.com/"}
])

onMounted(()=>{
  let c  = 0
  let time =0 ;
  const interval = setInterval(()=>{
    const counterH1 = document.querySelector(".container_load h1") as HTMLElement ;
if (counterH1) { c++;
 if (c>3) { counterH1.innerHTML = counterH1.innerHTML.slice(0,counterH1.innerHTML.length-3) ; c=0}
 else counterH1.innerHTML = counterH1.innerHTML + "." ;
  time++
if (time == 13) {gsap.to(".loader",{y:"-100%",duration:1})

   clearInterval (interval) ;
   window.scrollTo(0,0)
  }

}

  },600)
})
</script>

<template>
  <div class="main_app" style="overflow: hidden; ">
  <div class="loader">
    <div class="container_load">
  <div class="ball"></div>
  <div class="ball"></div>
  <div class="ball"></div>
  <div class="ball"></div>
  <div class="ball"></div>
  <div class="ball"></div>
  <div class="ball"></div>
  <h1 style="margin-top:50px;color: aliceblue;font-size:2vw;font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;"> PLEASE WAIT , RESSOURCES ARE BEING IMPORTED </h1>
</div>
  </div>
<Header></Header>
<Aboutme></Aboutme>  
<div class="projects" v-for="item in projects">
<Oneproject :number=item.number :name=item.name :description=item.description :link=item.link></Oneproject>
</div>
<Skills></Skills>
<Faq></Faq>
<ContactVue></ContactVue>
<footer style="width: 100% ; display: flex ;align-items: center; justify-content: center;font-family: sanshaa;"><p>CHECK THE <a href="https://github.com/Ahmedchammakhii/portfolio" target="_blank">GITHUB REPO</a> </p> <img style="height: 20px;width: auto;margin-left: 10px;" src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt=""></footer>
</div></template>
<style>
@font-face {
  font-family: "Valencia";
  src: local("Valencia"),
   url(./fonts/Valencia.ttf) format("truetype"); }
   @font-face {
  font-family: "sanshaa";
  src: local("sanshaa"),
   url(./fonts/sansha.ttf) format("truetype"); }
   @font-face {
  font-family: "avenir";
  src: local("avenir"),
   url(./fonts/Avenir.ttf) format("truetype"); }

html{
  overflow-x: hidden;
}
*{
  padding: 0;
  margin: 0;
}
:root {
  padding: 0;
  margin: 0;
  
}
h1,h3{
  padding: 0;
  margin: 0;
}
::-webkit-scrollbar {
  width: 10px;
}



::-webkit-scrollbar-thumb {
  background: #888; 
  border-radius: 2rem 4rem;
}


::-webkit-scrollbar-thumb:hover {
  background: #000000; 
}

.loader {
  width: 100%;
  height: 100%;
  min-height: 500vh;
  background-color: #000000;
  z-index: 1000;position:fixed ;
  top: 0;
}
.container_load{
	width:100vw;
	height: 100vh;
	padding-top: 100px;
display: flex;
flex-direction: column;
align-items: center;
}

.ball {
	width: 10px;
	height: 10px;
	margin: 10px auto;
	border-radius: 50px;
}

.ball:nth-child(1) {
	background: #ffffff;
	-webkit-animation: right 1s infinite ease-in-out;
	-moz-animation: right 1s infinite ease-in-out;
	animation: right 1s infinite ease-in-out;
}

.ball:nth-child(2) {
	background: #ffffff;
	-webkit-animation: left 1.1s infinite ease-in-out;
	-moz-animation: left 1.1s infinite ease-in-out;
	animation: left 1.1s infinite ease-in-out;
}

.ball:nth-child(3) {
	background: #ffffff;
	-webkit-animation: right 1.05s infinite ease-in-out;
	-moz-animation: right 1.05s infinite ease-in-out;
	animation: right 1.05s infinite ease-in-out;
}

.ball:nth-child(4) {
	background: #ffffff;
	-webkit-animation: left 1.15s infinite ease-in-out;
	-moz-animation: left 1.15s infinite ease-in-out;
	animation: left 1.15s infinite ease-in-out;
}

.ball:nth-child(5) {
	background: #ffffff;
	-webkit-animation: right 1.1s infinite ease-in-out;
	-moz-animation: right 1.1s infinite ease-in-out;
	animation: right 1.1s infinite ease-in-out;
}

.ball:nth-child(6) {
	background: #ffffff;
	-webkit-animation: left 1.05s infinite ease-in-out;
	-moz-animation: left 1.05s infinite ease-in-out;
	animation: left 1.05s infinite ease-in-out;
}

.ball:nth-child(7) {
	background: #ffffff;
	-webkit-animation: right 1s infinite ease-in-out;
	-moz-animation: right 1s infinite ease-in-out;
	animation: right 1s infinite ease-in-out;
}

@-webkit-keyframes right {
	0% {
		-webkit-transform: translate(-15px);
	}
	50% {
		-webkit-transform: translate(15px);
	}
	100% {
		-webkit-transform: translate(-15px);
	}
}

@-webkit-keyframes left {
	0% {
		-webkit-transform: translate(15px);
	}
	50% {
		-webkit-transform: translate(-15px);
	}
	100% {
		-webkit-transform: translate(15px);
	}
}

@-moz-keyframes right {
	0% {
		-moz-transform: translate(-15px);
	}
	50% {
		-moz-transform: translate(15px);
	}
	100% {
		-moz-transform: translate(-15px);
	}
}

@-moz-keyframes left {
	0% {
		-moz-transform: translate(15px);
	}
	50% {
		-moz-transform: translate(-15px);
	}
	100% {
		-moz-transform: translate(15px);
	}
}

@keyframes right {
	0% {
		transform: translate(-15px);
	}
	50% {
		transform: translate(15px);
	}
	100% {
		transform: translate(-15px);
	}
}

@keyframes left {
	0% {
		transform: translate(15px);
	}
	50% {
		transform: translate(-15px);
	}
	100% {
		transform: translate(15px);
	}
}
</style>

