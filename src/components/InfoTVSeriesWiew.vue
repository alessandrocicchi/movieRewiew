<script>
import axios from 'axios';
export default{ 
  data() {
    return {
      id: this.$route.params.id,
      series: []
    }
  },
  mounted(){
        axios
        .get('https://api.themoviedb.org/3//trending/tv/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
        .then(response => this.series = response.data.results)
    },
  methods: {
    
  },
  computed: {
    ReturnImage(){

      for (let i = 0; i < this.series.length; i++) {

        if (this.id==this.series[i].id) {

          return "https://image.tmdb.org/t/p/w500" + this.series[i].backdrop_path

        }
      }
    },
    ReturnTitle(){

      for (let i = 0; i < this.series.length; i++) {
        
        if (this.id==this.series[i].id) {
          
          return this.series[i].name
        }
      }
    },
    ReturnPopularity(){

      for (let i = 0; i < this.series.length; i++) {
        
        if (this.id==this.series[i].id) {
          
          return this.series[i].popularity
        }
      }
    },
    ReturnOverwiew(){

      for (let i = 0; i < this.series.length; i++) {
        
        if (this.id==this.series[i].id) {
          
          return this.series[i].overview
        }
      }
    },
    ReturnVoteAverage(){

      for (let i = 0; i < this.series.length; i++) {
        
        if (this.id==this.series[i].id) {
          
          return this.series[i].vote_average
        }
      }
    },
    ReturnVoteCount(){

      for (let i = 0; i < this.series.length; i++) {
        
        if (this.id==this.series[i].id) {
          
          return this.series[i].vote_count
        }
      }
    },
       
  }
}
</script>
<template>
  <!--
<img :href="ReturnImage" alt="Immagine">
 film.popularity 
Descrizione:{{ film.overview }}
Media voti:{{ film.vote_average }} 
Voti totali: {{ film.vote_count }}

  -->
<div class="container tabella">
    <div class="info">
        <div class="row">
            <img :href="ReturnImage" alt="Immagine">
        </div>
    <div class="row">
            <div class="col-6 colonna"> 
              Titolo:{{ ReturnTitle }}
            </div>
            <div class="col-6 colonna">
              Popolarità: {{ ReturnPopularity }} %  
            </div>
    </div>
    <div class="row">
      <div class="col">
        <div>
            <div class="col colonna"> 
              Descrizione:{{ ReturnOverwiew }} 
            </div>
        </div>
      </div>
    </div>
    <div class="row">
            <div class="col-6 colonna"> 
              Media voti:{{ ReturnVoteAverage }} 
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-bar-chart-fill" viewBox="0 0 16 16">
              <path d="M1 11a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v3a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1v-3zm5-4a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v7a1 1 0 0 1-1 1H7a1 1 0 0 1-1-1V7zm5-5a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1V2z"/>
            </svg>
            </div>
            
            <div class="col-6 colonna">
              Voti totali: {{ ReturnVoteCount }}  
              <span class="material-symbols-outlined">thumb_up</span>
            </div>
    </div>
  </div>
</div>
<br>
</template> 
<style>
.tabella{
  text-align: center;
}
.info{
  background-color: darkslategray;
    color: white;
    border: solid 5px black;
    text-align: center;
    font-size: medium;
    font-weight: bold;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
 }
 .colonna{
    font-size: larger;
    font-weight: bold;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    margin-top: 60px;
    margin-bottom: 60px;
    text-align: center;
 }
.material-symbols-outlined {
  color:white;
  font-variation-settings:
  'FILL' 0,
  'wght' 400,
  'GRAD' 0,
  'opsz' 48
}
</style>
<!--,
  mounted(){
        axios
        .get('https://api.themoviedb.org/3//trending/movie/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
        .then(response => console.log(this.$route.params.data))
    }-->

<!-- props: {
        title:{
            type: String 
        }
    }--> 