<script>
import axios from 'axios';
import { RouterLink, RouterView } from 'vue-router'
export default{ 
  data() {
    return {
      films: [],
    }
  },
  mounted(){    
          axios
          .get('https://api.themoviedb.org/3//trending/movie/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
          .then(response => this.films = response.data.results)        
    },
  methods: {
    ReturnImage(film){
      return "https://image.tmdb.org/t/p/w500" + film.backdrop_path
    },
    ReturnID(film){
      return film.id
    }
  }
}
</script>
<template>
  <br>
  <br>
  <br>
    <div class="container tabella">
    <div class="row" v-for="film in films" :key="film.id">
          <div class="col-4" style="color:white">
        </div>
        <div class="col-4">
          <div>
          <div class="card" style="width: 27rem; height: 22rem;">
            <img :src="ReturnImage(film)" class="card-img-top">
            <h5 class="card-title" style="font-weight: bold;">{{ film.title }}</h5>
            <h5 style="font-weight: bold;">Data di Rilascio: {{ film.release_date }}</h5>
            <router-link :to="{ name: 'info', params: { id: film.id } }"></router-link>
            <button class="btn btn-light btnCard" type="submit" @click="$router.push({ name: 'info', params: { id: film.id } })">INFO</button>
          </div>
          </div>
          <br>
        </div>
        <div class="col-4">
        </div>
    </div>
    <nav aria-label="Page navigation example">
      <ul class="pagination justify-content-center">
        <li class="page-item">
        </li>
        <RouterLink to="/"><li class="page-item"><a class="page page-link">1</a></li></RouterLink>
        <RouterLink to="/film2"><li class="page-item"><a class="page page-link" >2</a></li></RouterLink>
        
  </ul>
</nav>
  </div>
  </template>
<style>
.tabella{
  text-align: center;
}
.films {
  text-align: center;
}
.card {
  border: 5px solid black;
  background-color: black;
  color: red;
  text-align: center;
  font-weight: bold; 
}
.btnCard{
  font-weight: bold;
   height: 42px;
   width: 422px;
}
.btnCard:hover{
  color: white;
  background-color: red;
  font-weight: bold;
   height: 42px;
   width: 422px;
}
</style>
<!---->




