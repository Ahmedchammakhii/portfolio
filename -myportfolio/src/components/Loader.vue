<script setup lang="ts">
import { onMounted,onBeforeMount, ref } from 'vue';
import gsap from "gsap"

onMounted (()=> {
    var button = document.getElementById("play-pause-button") ;

gsap.to(".loading-bar",{width:"100%",duration:4 }
).then(()=>gsap.to(".loader",{y:"-100vh",transition:"all ease .1s",duration:1,  onComplete: () => {document.querySelector(".loader").style.display = "none";
  }}))


})

const doplay = ()=> {
    var audio = document.getElementById("myAudio") as HTMLAudioElement;
return audio.play()
}
</script>

<template>
<section class="loader" style="background: url('https://www.artnews.com/wp-content/uploads/2023/03/Pieter_BRUEGHEL_Ii_-_The_tax-collectors_office_-_Google_Art_Project.jpg?w=1920') no-repeat ;width: 100vw; height: 100vh;display: flex;flex-direction: column;align-items: center;justify-content: center;position: absolute;top: 0;">
<h1 >What about a lil bit of nostalgia while loading ressources ? </h1>
<div class="loading-bar-container">
        <div class="loading-bar"></div>
    </div> 

<img id="mediaplayer" src="https://www.apeaksoft.com/images/solution/windows-media-player-10.jpg" alt="Windows player">
<video id="loadervideo" style="position: absolute;scale: .25;transform: translateY(90px);" autoplay muted src="https://r4---sn-4g5lzned.googlevideo.com/videoplayback?expire=1694826784&ei=wKwEZc_7EIqt_9EPjdaO0Ac&ip=2607%3A5300%3A60%3A61a5%3Aae07%3A356d%3Aa2e0%3A18e3&id=o-AF9bfsC1ojphJ0deIVdm52SjDIJJaLxgs8c9Q-zMBhSj&itag=22&source=youtube&requiressl=yes&spc=UWF9f7B9vkT1MtPY2QjHr3jaS6Qbv28&vprv=1&svpuc=1&mime=video%2Fmp4&cnr=14&ratebypass=yes&dur=213.159&lmt=1687451967600849&fexp=24007246,24350018,24350026&beids=24350018&c=ANDROID&txp=6211224&sparams=expire%2Cei%2Cip%2Cid%2Citag%2Csource%2Crequiressl%2Cspc%2Cvprv%2Csvpuc%2Cmime%2Ccnr%2Cratebypass%2Cdur%2Clmt&sig=AOq0QJ8wRAIgQvbDh5fOXGBEtizg-qCFvI2D5G2pfBfRjxYBTL-dxxACIDF0V0p9Y8zuTsqHJEZe81o04eChp_yvfrqOvKdwjQK3&cm2rm=sn-bavc5aoxuuo-u0ol7e,sn-4g5e6z7e&req_id=3c018778d63a3ee&redirect_counter=2&cms_redirect=yes&cmsv=e&mh=zW&mip=197.26.60.153&mm=34&mn=sn-4g5lzned&ms=ltu&mt=1694804966&mv=m&mvi=4&pl=21&lsparams=mh,mip,mm,mn,ms,mv,mvi,pl&lsig=AG3C_xAwRQIhAJHBivAgXLB6yUdeNjJJzCtoTb0c6k0ZoJNO85mSA6zwAiA-0lfFWC692XmD7ys47XoeP7qwH-6-wHVRNqsWYpJVJQ%3D%3D"></video>
<audio style="transform: translateY(-80px) translateX(-120px);"  id="myAudio"  >
        <source src="/assets/mydream.mp3" type="audio/mpeg">
    </audio>
    <button @click="doplay()" class="play-button" id="play-pause-button"></button>

</section>

</template>
<style scoped>
.loader {
    color: white ;
    font-family: sanshaa;
    font-size: calc(.1rem + 1vw);
    font-weight: 200;
    text-align: center;

}
h1 {
}
#mediaplayer {
transform: scale(.9);
}
.loading-bar-container {
            width: 100%;
            height: 10px;
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
    h1 {
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
@media screen and (max-width:390px) {
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
}
audio::-webkit-media-controls-panel {
  display: none;
}
.play-button {
  width: 60px;
  height: 60px;
  background-color: #2196F3;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  position: relative;
  transition: background-color 0.3s ease-in-out;
  transform: translateX(-240px) translateY(-80px) scale(.6);
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
.play-button::after {
    content: "  PLAY NOW";
    position: absolute;
    top: 12px;
    left: 0;
}
</style>

