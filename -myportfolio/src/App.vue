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
,{number:'05', name:"EKOM", description:"A MODERN FULL E-COMMERCE IS CURRENTLY UNDER CONSTRUCTION ! STAY TUNED. ",link:"https://ekom.vercel.app/"}
])

onMounted(()=>{
const tl = gsap.timeline()
tl.to(".cube",{ transform: "rotateX(15deg) rotateY(25deg)",duration:3
}).to(".cube",{ transform: "rotateX(15deg) rotateY(40deg)",duration:2
}).to(".cube",{ transform: "rotateX(15deg) rotateY(60deg)",duration:2
}).to(".cube",{ transform: "rotateX(15deg) rotateY(110deg)",duration:2
}).to(".cube",{ transform: "rotateX(15deg) rotateY(130deg)",duration:2
}).to(".loader",{y:"-100%"}).then(()=>window.scrollTo(0,0))
})
</script>

<template>
  <div class="main_app" style="overflow: hidden; ">
  <div class="loader">
	<div class="cube">
            <div class="face">AHMED CHAMMAKHI</div>
            <div class="face">AHMED CHAMMAKHI</div>
            <div class="face">AHMED CHAMMAKHI</div>
            <div class="face">AHMED CHAMMAKHI</div>
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


.cube {
            position:fixed;
            transform-style: preserve-3d;
			transition: cubic-bezier(0.075, 0.82, 0.165, 1);
			top: 40%;
        }

        .face {
            position: absolute;
            width: 400px;
            height: 100px;
          
            line-height: 100px;
            font-size: 20px;
            color: #fff;
			letter-spacing: .8rem;
        }

        .face:nth-child(1) { transform: translateZ(400px) translateX(-20px) }
		.face:nth-child(2) { transform: rotateY(-90deg) translateZ(-200px) translateX(200px) }
		.face:nth-child(3) { transform: rotateY(-90deg) translateZ(250px) translateX(200px); }

        
      
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
  padding-left: 40%;
}
.container_load{
	width:100vw;
	height: 100vh;
	padding-top: 100px;
display: flex;
flex-direction: column;
align-items: center;
}
@media  screen and (max-width:400px) {
	.cube {
		scale:.2
	}
}

</style>

