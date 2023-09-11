<script setup lang="ts">
import { ref } from 'vue';

const train = ref("<Training>")
</script>

<template>
<div class="content_wrapper">
    
   <div class="left">
<h2>{{ train }}</h2>
    <h1>SKILLS</h1>
    <h2>{{ '</' + train.slice(1)  }}</h2>

</div>
<div class="right">
    <div class="set">
        <h2>HTML & CSS
</h2>
<h2>React
</h2>
<h2>ASTRO</h2>
<h2>NEXT JS</h2>
<h2>VUE JS</h2>
<h2>NODE JS</h2>
    </div>
    <div class="set">
        <h2>Project Management

</h2>
<h2>React
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
</div></div>
</template>
<style scoped>
.content_wrapper {
    width: 80vw;
    height: 60vh;
    display: flex;
font-family: avenir;
padding: 0 5%;
align-items: center;
}
.left {
    width: 50%;
}
.right {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
h1 {
    font-size: calc(4rem + 1vw);
}
</style>