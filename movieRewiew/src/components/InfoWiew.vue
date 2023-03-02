<script>
import axios from 'axios';
import { RouterLink} from 'vue-router'
export default{ 
  data() {
    return {
      id: this.$route.params.id,
      films: []
    }
  },
  mounted(){
        axios
        .get('https://api.themoviedb.org/3//trending/movie/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
        .then(response => this.films = response.data.results)
        
    },
  methods: {
    
  },
  computed: {
    ReturnImage(){

      for (let i = 0; i < this.films.length; i++) {

        if (this.id==this.films[i].id) {

          return "https://image.tmdb.org/t/p/w500" + this.films[i].poster_path

        }
      }
    },
    ReturnTitle(){

      for (let i = 0; i < this.films.length; i++) {
        
        if (this.id==this.films[i].id) {
          
          return this.films[i].title
        }
      }
    },
    ReturnPopularity(){

      for (let i = 0; i < this.films.length; i++) {
        
        if (this.id==this.films[i].id) {
          
          return this.films[i].popularity
        }
      }
    },
    ReturnOverwiew(){

      for (let i = 0; i < this.films.length; i++) {
        
        if (this.id==this.films[i].id) {
          
          return this.films[i].overview
        }
      }
    },
    ReturnVoteAverage(){

      for (let i = 0; i < this.films.length; i++) {
        
        if (this.id==this.films[i].id) {
          
          return this.films[i].vote_average
        }
      }
    },
    ReturnVoteCount(){

      for (let i = 0; i < this.films.length; i++) {
        
        if (this.id==this.films[i].id) {
          
          return this.films[i].vote_count
        }
      }
    },

  }
}
</script>
<template>
  <br>
  <br>
  <br>
  <div class="container tabella">
  <div class="row">
    <div class="col-5">
    <img :src="ReturnImage" alt="Immagine" style="height: 690px;width: 550px;">
  </div>
  <div class="col-7">
    <div class="infoF">
      <div class="row colonna" style="color: red;font-size: xx-large;">
        {{ ReturnTitle }}
      </div>
      <div class="row colonna">
        {{ ReturnOverwiew }}
      </div>
      <div class="row colonna">
        Visualizzazioni:{{ ReturnPopularity }}
      </div>
      <div class="row colonna">
        Media voti:{{ ReturnVoteAverage }}
      </div>
      <div class="row colonna">
        <div class="col-6">
        Voti:{{ ReturnVoteCount }}<span class="material-symbols-outlined">thumb_up</span>
        </div>
        <div class="col-6">
          <RouterLink to="/rewiew"><button class="btn btn-light" type="submit">LASCIA RECENSIONE</button></RouterLink>
        </div>
      </div>
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
.infoF{
  border: solid 5px black;
  background-color: black;
    color: white;
    font-size: large;
    font-weight: bold;
    text-align: left;
    height: 690px;
    width: 800px;
 }
 .colonna{
    font-size: large;
    font-weight: bold;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    text-align: left;
    padding: 30px;
 }
.material-symbols-outlined {
  color:white;
  font-variation-settings:
  'FILL' 0,
  'wght' 400,
  'GRAD' 0,
  'opsz' 48
}
.titolo{
  font-size: large;
  text-align: left;
}

</style>
<!--mounted(){
        axios
        .get('https://api.themoviedb.org/3//trending/tv/week?page=1&api_key=6f9286d54de4891ea7a5c91779e09786&language=it')
        .then(response => this.series = response.data.results)
    },--> 
    <!--
<img :href="ReturnImage" alt="Immagine">
 film.popularity 
Descrizione:{{ film.overview }}
Media voti:{{ film.vote_average }} 
Voti totali: {{ film.vote_count }}
  -->