<script setup lang="ts" >

const props = defineProps<{
  number: string;
  name: string;
  description: string;
}>();

import { onMounted, ref } from 'vue';
import ScrollTrigger from "gsap/ScrollTrigger";
import gsap from "gsap"
gsap.registerPlugin(ScrollTrigger);
onMounted(()=>{gsap.to( `.project-${props.number} span`,{duration:1,   x:"100%" , delay:.5 ,scrollTrigger : {
        trigger:`.project-${props.number}`,  toggleActions: "play reverse play reverse",
    }} )
    if(window.innerWidth>600)
{
    
    gsap.to (`.project-${props.number} .phone`,{y:"-40%", scale:1.1,scrollTrigger : {
        trigger:`.project-${props.number}`,
        toggleActions: "play reverse play reverse",    
     scrub: true, 
        
        
    }}) }
    else {
        gsap.to (`.project-${props.number} .phone`,{y:"-60%", scale:.4,scrollTrigger : {
        trigger:`.project-${props.number}`,
        toggleActions: "play reverse play reverse",    
     scrub: true, 
        
        
    }})
    }
    const effect = gsap.to(`.project-${props.number}`, {
        opacity: 0.7,
        y:"-15%",
        duration: 1,
      scrollTrigger:{
        trigger: '.end-'+props.number, 
        end: 'bottom bottom', 
        onLeave: () => {
            effect.play()
      
            
},

        toggleActions: "play reverse play reverse",    

      }
      });



})
const getimg = (img : string)=> {
    return "/assets/"+props.name+'/'+img
}

</script>

<template>
<article :class="'project-'+number">
<div class="top_container">
    <p class="parag">{{number}} <span></span></p>
</div>
<div class="wrapper">
<div class="content_wrapper">
    <div class="title">
       <p class="parag">{{name}} <span></span></p>  
    </div>
    <div class="tags">
        <div class="dot"></div>
        <div class="content">
           <p class="parag">FULL STACK DEV <span></span></p> 
        </div>
        <div class="dot"></div>
    </div>
    <div class="description">
       <p class="parag">{{description}} <span></span>
    </p></div>
</div>
<div class="photos_wrapper">
    <img class="phone" :src="getimg('Iphone.png')" alt="uphone">

    <img class="phone" :src="getimg('Iphone(1).png')" alt="uphone">
    <img class="phone" :src="getimg('Iphone(2).png')" alt="uphone">
    <img class="phone" :src="getimg('Iphone(3).png')" alt="uphone">

</div>
</div>
<div class="end" style="height: 30vh;"></div>
</article><div :class="'end-'+number" style="margin-bottom: 30vh;"></div>

</template>

<style scoped>
article {

    width: 80vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
font-family: avenir;
padding: 0 5%;
}
.top_container p {
    font-size: calc(2rem + 1vw);
    width: max-content
}
.title {
    color:#333333;
    font-size: calc(5rem + 2vw);
}
.content_wrapper {
    display: flex;
    flex-direction: column;   justify-content: flex-end;
gap: 20px;
    height: 80%;
    width: 70%;
}
.tags {
    display: flex;
    gap: 10px;
    align-items: center;
    color: #333333;
    font-size: calc(.7rem + .5vw);
}
.dot {
    background: #090909;
    height: 7px;
    width: 7px;
    border-radius: 50%;
}
.wrapper {
    width: 100%;
    height: 100%;
    display: flex;
    padding-bottom: 200px;
}
.description {
    font-size: calc(1rem + 1vw);
    opacity: .7;
    font-family: sanshaa;
}
.photos_wrapper {
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-template-rows: repeat(2,1fr);
    gap: 20px;
    
}
.phone {
    height: 400px;
    width: auto;
}
.phone:nth-child(1) {
    transform: translateY(100px);
    height: 500px;

} 
.phone:nth-child(4) {
    transform: translateY(-50px);

}
.phone:nth-child(3) {
    scale: .7 ;
    transform: translateY(100px);

}
p {
    position: relative;
    margin: 0;
    padding: 0;
    overflow: hidden;
    width: max-content;
}
.description p {
    max-width: 90%;

}
span{
    position: absolute;
    content: "";
    width: 100%;
    height: 100%;
    background-color: #090909;
    left: 0;
}
@media screen and (max-width:1200px) {
    .phone {
        transform: scale(.7);
    }
}
@media screen and (max-width:900px) {
    .wrapper {
        position: relative;
    }
    .photos_wrapper{
        position: absolute;
        left: -10%;

    }
    .phone {
        transform: scale(.5);
    }

}
@media screen and (max-width:600px) {
    video {
        display: none;
    }
    .phone {
        transform: scale(.4);
    }
    .photos_wrapper {
   
    row-gap: 60px;
    column-gap: 10px;
    
}
}

</style>