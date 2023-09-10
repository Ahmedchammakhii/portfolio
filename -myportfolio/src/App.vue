<script setup lang="ts">
import Aboutme from './components/Aboutme.vue';
import Header from './components/Header.vue'
import Oneproject from './components/Oneproject.vue';
</script>

<template>
<Header></Header>
<Aboutme></Aboutme>  
<Oneproject></Oneproject>
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

