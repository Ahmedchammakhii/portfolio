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
        console.log(data);
        
        const datatemp = {
            name : data.value.name ,
            email : data.value.email , 
            message : data.value.message , 
            to_name:"ahmed"

        }
      emailjs.send("service_8xz21y9", "template_f514fhg", datatemp, "2GESCxzoh06lJKiVv")
        .then((response : any) => {
display.value=!display.value      })
        .catch((error : any) => {
    console.log(error);
    
        });
    }

</script>

<template>
    <address class="content_wrapper__contact">
<h1>{{ "<"+contactTag+">" }}</h1>
<p>Feel free to send an e-mail on Ahmedchammakhi2@gmail.com , to Contact me on +21698648548 or to check my <a href="https://drive.google.com/file/d/1Qtg6_Sl8ThQaqoB19zTXJ9BiHMGRZBps/view?usp=sharing"> CV </a></p>
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
textarea{

    height: 10vh;
}

button {
    width: 40%;
    height: 5vh;
    margin: 50px 0;
    background-color: transparent;
    border-color: #333333;
    border-radius: 2rem 5rem;
}
@media screen and (max-width:600px) {
    input , textarea{
    width: 90%;
  
}
button {
    width: 90%;
color: black;
}

}

</style>