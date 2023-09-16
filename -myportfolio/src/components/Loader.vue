<script setup lang="ts">
import { onMounted,onBeforeMount, ref } from 'vue';
import gsap from "gsap"

const props = defineProps<{
  istrue : boolean
}>();
onMounted (()=> {
    var button = document.getElementById("play-pause-button") ;
const loader = document.querySelector(".loader") as HTMLElement | null;
gsap.to(".loading-bar",{width:"100%",duration:4 }
)


})
const doplay = ()=> {
    var audio = document.getElementById("myAudio") as HTMLAudioElement;
return audio.play()
}
</script>

<template>
<section class="loader" v-if="istrue == false" style="width: 100vw; height: 100vh;display: flex;flex-direction: column;align-items: center;justify-content: center;position: absolute;top: 0;">
<!-- <h1 >What about a lil bit of nostalgia while loading ressources ? </h1>


<img id="mediaplayer" src="/assets/windows-media-player-10.jpg" alt="Windows player">
<video id="loadervideo" style="position: absolute;scale: .25;transform: translateY(90px);" autoplay muted src="https://r4---sn-4g5lzned.googlevideo.com/videoplayback?expire=1694826784&ei=wKwEZc_7EIqt_9EPjdaO0Ac&ip=2607%3A5300%3A60%3A61a5%3Aae07%3A356d%3Aa2e0%3A18e3&id=o-AF9bfsC1ojphJ0deIVdm52SjDIJJaLxgs8c9Q-zMBhSj&itag=22&source=youtube&requiressl=yes&spc=UWF9f7B9vkT1MtPY2QjHr3jaS6Qbv28&vprv=1&svpuc=1&mime=video%2Fmp4&cnr=14&ratebypass=yes&dur=213.159&lmt=1687451967600849&fexp=24007246,24350018,24350026&beids=24350018&c=ANDROID&txp=6211224&sparams=expire%2Cei%2Cip%2Cid%2Citag%2Csource%2Crequiressl%2Cspc%2Cvprv%2Csvpuc%2Cmime%2Ccnr%2Cratebypass%2Cdur%2Clmt&sig=AOq0QJ8wRAIgQvbDh5fOXGBEtizg-qCFvI2D5G2pfBfRjxYBTL-dxxACIDF0V0p9Y8zuTsqHJEZe81o04eChp_yvfrqOvKdwjQK3&cm2rm=sn-bavc5aoxuuo-u0ol7e,sn-4g5e6z7e&req_id=3c018778d63a3ee&redirect_counter=2&cms_redirect=yes&cmsv=e&mh=zW&mip=197.26.60.153&mm=34&mn=sn-4g5lzned&ms=ltu&mt=1694804966&mv=m&mvi=4&pl=21&lsparams=mh,mip,mm,mn,ms,mv,mvi,pl&lsig=AG3C_xAwRQIhAJHBivAgXLB6yUdeNjJJzCtoTb0c6k0ZoJNO85mSA6zwAiA-0lfFWC692XmD7ys47XoeP7qwH-6-wHVRNqsWYpJVJQ%3D%3D"></video>
<audio style="transform: translateY(-80px) translateX(-120px);"  id="myAudio"  >
        <source src="/assets/mydream.mp3" type="audio/mpeg">
    </audio>
    <button @click="doplay()" class="play-button" id="play-pause-button"></button> -->
    <audio style="transform: translateY(-80px) translateX(-120px);"  id="myAudio"  >
        <source src="/assets/mydream.mp3" type="audio/mpeg">
    </audio>

    <div class="firefly">
    <button @click="doplay()" class="play-button" id="play-pause-button"></button>
<div class="glow"></div>
  <p>some nostalgia maybe ?</p>

</div>
<div class="loading-bar-container">
        <div class="loading-bar"></div>
    </div> 
    <p>Loading ressources ! please wait</p>
</section>

</template>
<style >

.loader {
    color: white ;
    font-family: sanshaa;
    font-size: calc(.1rem + 1vw);
    font-weight: 200;
    text-align: center;
    background: #222;
}


.firefly, .firefly div {
  position: relative;
}

.firefly {
  width: 20px;
  height: 20px;
  border-radius: 70px 70px 0 0;
  margin: 10% auto;
  z-index: 1;
  
  animation: move 5s ease infinite;
  -moz-animation: move 5s ease infinite;
  -webkit-animation: move 5s ease infinite;
  -o-animation: move 20s ease infinite;
}

.head{
  background:#1A1515;
  height:10px;
  width:20px;
  border-radius: 90px 90px 0 0;
  -moz-border-radius: 90px 90px 0 0;
  -webkit-border-radius: 90px 90px 0 0;
  top:35px;
  z-index:4;
  
}


.glow {
  border-radius: 0 0 70px 70px;
  width: 60%;
  height: 70%;
  background: #FBFF7A;
  margin: 0 auto;
  z-index: 2;
  animation: glowing 1s linear infinite alternate;
  -webkit-animation: glowing 1s linear infinite alternate;
  transition: 1s all;
}



@keyframes glowing {
  from {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 50px 10px #E8D500, inset 0 0 80px 80px #FFED24;
  }
  to {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 100px 10px #E8D500, inset 0 0 50px 50px #FFED24;
  }
}

@-webkit-keyframes glowing {
  from {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 50px 10px #E8D500, inset 0 0 80px 80px #FFED24;
  }
  to {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 130px 10px #E8D500, inset 0 0 50px 50px #FFED24;
  }
}

@-moz-keyframes glowing {
  from {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 50px 10px #E8D500, inset 0 0 80px 80px #FFED24;
  }
  to {
    box-shadow: inset 0 0 20px 20px #E8D500, 0 0 130px 10px #E8D500, inset 0 0 50px 50px #FFED24;
  }
}


@keyframes move
{
0%   {left:0px; top:0px; transform: rotate(45deg);}
50%{left: 0px; top:0px; transform: rotate(-45deg);}
100% {left: 0px; top:0px; transform: rotate(45deg);}
}

@-webkit-keyframes move 
{
0%   {left:0px; top:0px; -webkit-transform: rotate(45deg);}
50%{left: 0px; top:0px;  -webkit-transform: rotate(-45deg);}
100% {left: 0px; top:0px;  -webkit-transform: rotate(45deg);}
}

@-moz-keyframes move 
{
0%   {left:0px; top:0px; -moz-transform: rotate(45deg);}
50%{left: 0px; top:0px;  -moz-transform: rotate(-45deg);}
100% {left: 0px; top:0px;  -moz-transform: rotate(45deg);}
}

@-o-keyframes move
{
0%   {left:0px; top:0px; -webkit-transform: rotate(45deg);}
50%{left: 0px; top:0px;  -webkit-transform: rotate(-45deg);}
100% {left: 0px; top:0px;  -webkit-transform: rotate(45deg);}
}
#mediaplayer {
transform: scale(.9);
}
.loading-bar-container {
            width: 100%;
            height: 50px;
            background-color: #ddd;
            position: relative;
            scale: .5;
        }

        .loading-bar {
            width: 0;
            height: 100%;
            background-color: #000000;
            position: absolute;
            transition: width 0.5s ease-in-out;
        }
@media screen and (max-width:650px) {
    .loader h1 {
    position: relative;
    font-size: calc(.8rem + 1vw);

    }

     #mediaplayer {
transform: scale(.6);
}
#loadervideo {
    transform: scale(.2) translateY(110px) !important;

}
}
/* @media screen and (max-width:390px) {
#loadervideo {
    transform: scale(.2) translateY(200px) !important;

}
}
@media screen and (max-width:650px) {
     #mediaplayer {
transform: scale(.45);
}
#loadervideo {
    transform: scale(.1) translateY(110px) !important;

}
} */
audio::-webkit-media-controls-panel {
  display: none;
}
.play-button {
  width: 20px;
  height: 20px;
  background-color: #2196F3;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  position: relative;
  transition: background-color 0.3s ease-in-out;
}

.play-button:before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-40%, -50%);
  border-style: solid;
  border-width: 12px 0 12px 24px;
  border-color: transparent transparent transparent white;
}

.play-button.playing:before {
  border-width: 0;
  width: 12px;
  height: 24px;
  background-color: white;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.play-button:hover {
  background-color: #0D47A1;
}

</style>

