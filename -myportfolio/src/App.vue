<script setup lang="ts">
import { ref } from 'vue';
import Aboutme from './components/Aboutme.vue';
import Header from './components/Header.vue'
import Oneproject from './components/Oneproject.vue';
import Skills from "./components/Skills.vue"
import  ContactVue from './components/Contact.vue';
const projects=ref([{number:'01', name:"KAIZEN TN", description:" PORTFILO FOR A DIGITAL COMPANY MADE WITHIN 2 DAYS"}
, {number:'02', name:"5I", description:" SUPER-IINTERACTIVE WEBSITE BUILT FOR A BRANDING AGENCY"}
,{number:'03', name:"AFRAH", description:" WEBSITE BUILT FOR A WEDDING PLANNER USING NEXTJS"}
])
</script>

<template>
<Header></Header>
<Aboutme></Aboutme>  
<div class="projects" v-for="item in projects">
<Oneproject :number=item.number :name=item.name :description=item.description></Oneproject>
</div>
<Skills></Skills>
<ContactVue></ContactVue>
<footer style="width: 100% ; display: flex ;align-items: center; justify-content: center;font-family: sanshaa;"><p>CHECK THE <a href="https://github.com/Ahmedchammakhii/portfolio" target="_blank">GITHUB REPO</a> </p> <img style="height: 20px;width: auto;margin-left: 10px;" src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt=""></footer>
</template>
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
   url(./fonts/avenir.ttf) format("truetype"); }

html{
  overflow-x: hidden;
}
h1,h3{
  padding: 0;
  margin: 0;
}
</style>

