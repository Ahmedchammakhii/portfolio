<script setup lang="ts">
import { ref } from 'vue';
import emailjs from "emailjs-com"
const contactTag=ref("contact")
const display= ref(true)
const  data = ref( {
        name: "",
        email: "",
        message: "",
      })
      const submitForm =()=> {
      emailjs.send("service_8xz21y9", "template_f514fhg", {...data,to_name:"ahmed"}, "2GESCxzoh06lJKiVv")
        .then((response) => {
display.value=!display.value      })
        .catch((error) => {
    console.log(error);
    
        });
    }

</script>

<template>
    <address class="content_wrapper__contact">
<h1>{{ "<"+contactTag+">" }}</h1>
<p>THIS WEBSITE IS CREATED TO ONLY APPLY FOR THE JOB SUBMITTED BY <a href="https://tanitjobs.com/job/1355515/d%C3%A9veloppeur-front-end-vue-js/?backPage=&searchID=1693557052.2987" target="_blank"> FANPRIME </a> </p>
<p>Feel free to send an e-mail on Ahmedchammakhi2@gmail.com Or Contact me on +21698648548</p>
<form v-if="display==true" @submit.prevent="submitForm">
    <label for="name">Name:</label>
    <input type="text" id="name" v-model="data.name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" v-model="data.email" required>
    
    <label for="message">Message:</label>
    <textarea id="message" v-model="data.message" required></textarea>
    
    <button type="submit">Submit</button>
  </form>
  <h1 v-if="display==false">THANKS FOR REACHING OUT !</h1>
<h1 >{{ "<"+contactTag+"/>" }}</h1>

    </address>
</template>
<style scoped>

.content_wrapper__contact{
    height:90vh;
    font-family: avenir;
    padding-top:7% ;
    padding-left: 5%;
    display: flex;
    flex-direction: column;

}
form {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
input , textarea{
    width: 40%;
    height: 4vh;
padding: 10px;
}
button {
    width: 40%;
    height: 5vh;
    margin: 50px 0;
    background-color: transparent;
    border-color: #333333;
    border-radius: 2rem 5rem;
}
</style>