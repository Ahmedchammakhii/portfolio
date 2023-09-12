<script setup lang="ts">
import { onMounted, ref } from 'vue';
import ScrollTrigger from "gsap/ScrollTrigger";
import gsap from "gsap"
const train = ref("<Training>")
    onMounted(()=>{
const timeline = gsap.timeline()
timeline.to("video",{scale:10,scrollTrigger:{
    trigger:".endoftimeline",
    end:"bottom bottom",
    scrub:true
}})
timeline.to(".right_quote",{
    opacity:0,scrollTrigger:{
    trigger:".endoftimeline",
    end:"bottom bottom",

    scrub:true,
}
},"+=5").to(".right",{
    opacity:1,scrollTrigger:{
    trigger:".endoftimeline",
    end:"bottom bottom",

    scrub:true,
}
},"+=15")
gsap.to(".content_wrapper__skills",{opacity:0,scrollTrigger:{
        trigger:".content_wrapper__contact"
        , start:"top 70%",
        scrub:true
    }})
    })
   
    // let isTrue = ref(false)

// const handleAnimationEnd = () => {
//    const element = document.querySelector(".right_quote")

//     if (element) {
//     element.style.opacity=0;
//     }
//     isTrue.value = !isTrue.value ;
//     console.log(isTrue.value);
    
// }

</script>

<template>
<div class="content_wrapper__skills">
    
   <div class="left">
<h2>{{ train }}</h2>
    <h1>SKILLS</h1>
    <h2>{{ '</' + train.slice(1)  }}</h2>

</div>
<div class="right" >
    <div class="set">
        <h2>HTML & CSS
</h2>
<h2>React
</h2>
<h2>ASTRO</h2>
<h2>NEXT JS</h2>
<h2>VUE JS *Thanks to fanprime*</h2>
<h2>NODE JS</h2>
    </div>
    <div class="set">
        <h2>Project Management

</h2>
<h2>Visual Communication
</h2>
<h2>Concept development</h2>

    </div>
    <div class="set">
        <h2>Figma</h2>
        <h2>Photoshop</h2>
        <h2>After effect</h2>
    </div>
</div>
<div class="right_quote" >
    <h1>,,</h1>
    <p>Majority of people can
run a 100meter dash,
but only a dozen can
do it in under 9.8
seconds</p>
<h1>,,</h1>

</div>
<video autoplay muted >
  <source src="/assets/videos/ch.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video></div>
<div class="endoftimeline" style="height: 20vh;"></div>
</template>
<style scoped>
.content_wrapper__skills {
    width: 90vw;
    height: 60vh;
    display: flex;
font-family: avenir;
padding-left: 5%;
align-items: center;
}
.left {
    width: 50%;
}
.right {
    display: flex;
    flex-direction: column;
    gap: 20px;
opacity: 0;
}
h1 {
    font-size: calc(3rem + 1vw);
}
.right_quote p {
    font-size: calc(2rem + 1vw);
text-align: center;
}
.right_quote {
    width: 70%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.right_quote h1:nth-last-child(1){
    width: 100%;
    display: flex;
    justify-content: flex-end;
}
video {
    width: 150px;
    height: 100px;
    border-radius: 50%;
    object-fit: cover;
    transition: all ease 5s;
margin-left: 100px;
}
@media screen and (max-width:1360px) {
    video {
        transform: scale(.8);
    }
}
@media screen and (max-width:900px) {
    video {
        display: none;
    }
}

@media screen and (max-width:600px) {
    .right_quote {
        display: none;
    }
    .right{
        margin-left: 50px;
    }
    .set h2 {
        font-size: calc(1rem + .8vw);
    }
}
</style>