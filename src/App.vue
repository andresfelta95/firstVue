<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <HelloWorld msg="Peliculas"/>
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
  
  html, 
  body {
    
    background: blue;
    margin: 0;
    font-family: sans-serif;
    color: white;
  }
  
  h2{
    text-align: center;
    border-bottom: 1px solid white;
    color: white;
    padding-bottom: 10px;
}
</style>
