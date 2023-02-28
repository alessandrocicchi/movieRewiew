<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Navbar from './components/Navbar.vue'
import Container from './components/Container.vue'
</script>

<template>
  <thead>
<Navbar />
</thead>
<tbody>
<Container />
</tbody>
    
  <RouterView />
</template>

<style>

</style>
