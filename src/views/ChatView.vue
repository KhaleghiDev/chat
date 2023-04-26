<script setup>
import TheChat from '../components/TheChat.vue'
import axios from 'axios'
function listchat(){
  axios.get('http://localhost/openAi/api/chat/project/list')
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
}
listchat
</script>
<template>
   
      <TheChat/>

  </template>
  
  <style>

  </style>
  