<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Aboutme from './components/Aboutme.vue';
import Header from './components/Header.vue'
import Oneproject from './components/Oneproject.vue';
import  ContactVue from './components/Contact.vue';
import Faq from './components/Faq.vue';
import gsap from 'gsap';
import {defineAsyncComponent} from 'vue'
const Skills = defineAsyncComponent(
  ()=>import ("./components/Skills.vue")
)
const projects=ref([{number:'01', name:"VAWZEN", description:" PORTFILO FOR A DIGITAL COMPANY MADE WITHIN 2 DAYS",link:"https://vawzen.org/"}
, {number:'02', name:"5I", description:" SUPER-IINTERACTIVE WEBSITE BUILT FOR A BRANDING AGENCY",link:"https://5i.vercel.app/"}
,{number:'03', name:"AFRAH", description:" WEBSITE BUILT FOR A WEDDING PLANNER USING NEXTJS",link:"https://afrah-eta.vercel.app/"}
,{number:'04', name:"E-TAFAKNA", description:"I PLAYED A PIVOTAL ROLE AS A TECH LEAD IN THE DEVELOPMENT OF TWO CUTTING-EDGE APPLICATIONS AND A ROBUST PLATFORM. ",link:"https://e-tafakna.com/"}
,{number:'05', name:"EKOM", description:"A MODERN FULL E-COMMERCE IS CURRENTLY UNDER CONSTRUCTION ! STAY TUNED. ",link:"https://ekom.vercel.app/"}
])

onMounted(()=>{
  
})</script>

<template>
  <div class="main_app" style="overflow: hidden; ">
<div class="loader">

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


</style>

