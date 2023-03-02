<script setup>
import {RouterView } from 'vue-router'
import Navbar from './views/Navbar.vue'
import Container from './views/Container.vue'
</script>

<template>
  <div id="app">
    <div>
      <Navbar />
    </div>
    <div>
      <Container />
    </div>
  </div>    
  <RouterView />
</template>

<style>

</style>
