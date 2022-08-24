<template>
  <div id="app">
    <img alt="Pokemon logo" src="./assets/Pokemon.png">
    <Pokeapi msg="Bienvenido a tu Guía Pokemon"/>
  </div>
</template>

<script>
import Pokeapi from './components/Pokeapi'

export default {
  name: 'App',
  components: {
    Pokeapi
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #be0029;
  margin-top: 60px;
}
</style>
