<script setup lang="ts">

</script>

<template>
    <header>
  <div class="greetings">
    <h1>Chammakhi ahmad</h1>
    <h3>FULL STACK DEVELOPER </h3>
  </div>
    </header>
</template>

<style scoped>
@font-face {
  font-family: "Valencia";
  src: local("Valencia"),
   url(../fonts/Valencia.ttf) format("truetype"); }
   @font-face {
  font-family: "sanshaa";
  src: local("sanshaa"),
   url(../fonts/sansha.ttf) format("truetype"); }
h1 {
    font-family: Valencia;
    font-size: calc(6rem + 2vw);
    font-weight: 200;
}
h3{
    font-family: sanshaa;   
    font-size: calc(1rem + .7vw);

}
.greetings {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    
}
</style>
