<script setup>
import TheChat from "../components/TheChat.vue";
import axios from "axios";
import { ref } from "vue";
let lists = ref([]);
let errors = ref();
const listenChat = async ()=> {
  await axios
    .get("http://openai.test/api/chat/project/list", {
      headers: {
        Accept: "application/json",
      },
    })
    .then(function (response) {
      // handle success
      // console.log(response.data);
      // console.log(response.data)
      if(response.data.meta.status ==1){
        
        lists.value =  response.data.data
        console.log(lists);
      }else{
        errors.value =response.data
        console.log(errors);
      }
    })
    .catch(function (error) {
      // handle error
      console.log(error);
    });
  }

listchat;
</script>
<template>
  <TheChat :lists="lists"/>
</template>
  
  <style>
</style>
  