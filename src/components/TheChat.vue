<script setup>
import { ref } from 'vue';

defineProps(['lists']);
let mydata = ref("");

// const showDate = (id) => {

// }
let serchData=async()=>{
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
     
        
        lists.value =  response.data.data
        console.log(lists);
   
    })
    .catch(function (error) {
      // handle error
      console.log(error);
    });
    console.log(mydata.value);
  }


// setInterval(() => {
//   console.log(mydata.value);
// }, 1000);
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col-md-4 col-sm-12 col-xs-12">
          <button class="btn btn-success m-2">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-plus"
              viewBox="0 0 16 16">
              <path
                d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z" />
            </svg>
          </button>
        <div class="serch">
          <div class="mb-3">
            <input type="serch" class="form-control" name="serch" id="serch" @keydown.enter="serchData"   aria-describedby="serchHelp"
              placeholder="جستجو کنید ..." v-model="mydata">
          
          
          </div>
        </div>
        <!-- card -->
        <div v-for="(item, index) in lists " :key="index">
          <!-- {{ item }} -->
          <div class="card mb-3" style="max-width: 540px;">
            <div class="row g-0">
              <div class="col-12">
                <img v-if="item.image === null" src="@/assets/chat/img/logo.png" width="64" height="64"
                  class="img-fluid rounded-start" alt="{{ item.title }}">
                <img v-else src="item.image" class="img-fluid rounded-start" alt="{{ item.title }}">
              </div>
              <div class="col-md-8">
                <div class="card-body">
                  <a href="">
                    <h5 class="card-title" @click="showDate(item.id)">{{ item.title }}</h5>
                  </a>
                  <p class="card-text">{{ item.description }}</p>
                  <p class="card-text">{{ item.phone }}</p>
                  <a :href="item.domin">{{item.domin }} </a>
                  {{ item }}
                  <p class="card-text"><small class="text-body-secondary">{{ item.created_at }}</small></p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- card -->
        <!-- show data projeact -->

        <!-- show data projeact -->

      </div>
      <div class="col-md-8 col-sm-">

      </div>
    </div>
  </div>
</template>
