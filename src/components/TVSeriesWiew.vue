<script>
import axios from 'axios';
import { RouterLink, RouterView } from 'vue-router'
export default{ 
  data() {
    return {
      series: [],
    }
  },
  mounted(){
        axios
        .get('https://api.themoviedb.org/3//trending/tv/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
        .then(response => this.series = response.data.results)
    },
  methods: {
    ReturnImage(serie){
      return "https://image.tmdb.org/t/p/w500" + serie.backdrop_path
    }
  }
}
</script>
<template>
    <div class="container tabella">
    <div class="row" v-for="serie in series" :key="serie.id">

      <div class="col-4">
      </div>
      <div class="col-4">
        <div>
        <div class="card" style="width: 27rem; height: 22rem;">
          <img :src="ReturnImage(serie)" class="card-img-top">
          <h5 class="card-title">{{ serie.name }}</h5>
          <h5>Data di Rilascio: {{ serie.first_air_date }}</h5>
          <router-link :to="{ name: 'infoTVSeries', params: { id: serie.id } }"></router-link>
          <button class="btn btn-dark" type="submit" @click="$router.push({ name: 'infoTVSeries', params: { id: serie.id } })" style="font-weight: bold; height: 42px;width: 424px;">INFO</button>
        </div>
        </div>
        <br>
      </div>
      <div class="col-4">
      </div>
    </div>
  </div>
  </template>
<style>
.tabella{
  text-align: center;
  background-image: linear-gradient(to right, black, white);
}
.films {
  text-align: center;
}
.card {
  border: 5px solid black;
  background-color: darkslategrey;
  color: white;
  text-align: center;
  font-weight: bold;
}
</style>
<!--this.films = response.data.results
<div v-for="post in posts" :key="post.id">
    <h2>{{ post.id }} {{ post.title }}</h2>
    <p>{{ post.body }}</p>
  </div>
  .get('https://jsonplaceholder.typicode.com/posts') da inserire nella funzione mounted()
  data() {
    return {
      posts: []
    }
  },-->
  <!--<section>
    <form @submit.prevent="createPost">
      <div>
        <label for="userId">UserID:</label>
        <input type="text" id="userId" v-model="postData.userId">
      </div>
      <div>
        <label for="title">Title:</label>
        <input type="text" id="title" v-model="postData.title">
      </div>
      <div>
        <label for="body">Body:</label>
        <textarea id="body" rows="6" cols="22" v-model="postData.body"></textarea>
      </div>
      <button>Create Post</button>
    </form>
  </section>
  .post('https://jsonplaceholder.typicode.com/posts', this.postData)
  data() {
    return {
      postData: { userid: '', title: '', body: '' }
    }
  },
   
  methods: {

    createPost(){
        axios
        .post('https://jsonplaceholder.typicode.com/posts', this.postData) 
        .then(response =>console.log(response))
    }
  }
  -->
  <!-- METODO PUT
  mounted(){
        axios
        .put('https://jsonplaceholder.typicode.com/posts/1',{
          id:'1',
          userId: '1',
          title: 'Article Title',
          body: 'Article body'
        }) 
        .then(response =>console.log(response))
  }-->
  <!-- METODO PATCH
    mounted(){
        axios
        .patch('https://jsonplaceholder.typicode.com/posts/1',{
          title: 'Article Title',
        }) 
        .then(response =>console.log(response))
  }-->

  <!-- METODO DELETE
  mounted(){
        axios
        .delete('https://jsonplaceholder.typicode.com/posts/1') 
        .then(response =>console.log(response))
  }-->

  <!-- METODO ERROR
  mounted(){
        axios
        .get('https://jsonplaceholder.typicode.com/wrong') 
        .catch(error => console.log(error))
  }-->




