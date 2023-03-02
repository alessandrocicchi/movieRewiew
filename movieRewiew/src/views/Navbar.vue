<script>

export default{

  data() {

  },
  computed: {

  },
  methods: {
    cercaFilm(){
      
    }
  }
}
</script>

<template>
        <nav class="navbar navbar-expand-xl fixed-top" style="background-color: lightslategray;">
    <div class="container-fluid">
      <span class="material-symbols-outlined">movie_filter</span>
      <a class="navbar-brand" href="#" style="color: black;font-weight: bold;">Movie Rewiew</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <RouterLink to="/"><a class="nav-link home" aria-current="page">Home</a></RouterLink>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" role="button" data-bs-toggle="dropdown" aria-expanded="false" style="font-weight: bold;font-size:large;color: black;">
              Categorie
            </a>
            <ul class="dropdown-menu" style="font-weight: bold;background-color: white;">
              <li><RouterLink to="/"><a class="dropdown-item menu" href="#">Film</a></RouterLink></li>
              <li><RouterLink to="/TVseries"><a class="dropdown-item menu" href="#">Serie TV</a></RouterLink></li>
              <li></li>
            </ul>
          </li>
        </ul>
        <form class="d-flex" role="search">
          <input class="form-control me-2" type="search" placeholder="Cerca" aria-label="Search" style="font-size: medium;">
          <button class="btn btn-outline-dark" type="submit" style="font-size: medium;" @click="cercaFilm">Cerca</button>
        </form>
      </div>
    </div>
  </nav>
  </template>
<style>
.tabella{
  width: 100%;
  height: 100%;
  text-align: center;
  margin-left: -10rem;
  margin-right: 100rem;
}
.home{
  color: white;
  font-weight: bold;
  font-size:large;
}
.home:hover{
  color: red;
  font-weight: bold;
  font-size:large;
}
.material-symbols-outlined {
  color: red;
  font-variation-settings:
  'FILL' 0,
  'wght' 400,
  'GRAD' 0,
  'opsz' 48
  
}
.menu{
  font-weight: bold;
  font-size:large;
  background-color: white;
  color: black;
}
.menu:hover{
  background-color: red;
  color: white;
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




