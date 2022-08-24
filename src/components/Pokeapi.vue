<template>
  <div id="app">
    <h1>Poke Guía</h1>
   <p>Nombre</p> 
   <input v-model="pokemonName"   type="text" placeholder="Busca un Pokemon">
   <button @click="searchPokemon">Buscar</button>

       <img v-if="currentPokemon.sprites" :src="currentPokemon.sprites.front_default">

   <h2>Moves</h2>
   <ul>
       <li v-for="move in currentPokemon.moves" :key="move.name">
           {{move.move.name}}
       </li>
       <li></li>
   </ul>
   <h2>Abilities</h2>
   <ul>
       <li v-for="ability in currentPokemon.abilities" :key="ability.name">
           {{ability.ability.name}}
       </li>
   </ul>
  </div>
</template>

<script>
export default {
  data(){
    return {
      currentPokemon: {},
      pokemonName: ""
    }
  },
  created(){
    fetch(`https://pokeapi.co/api/v2/pokemon/pikachu`)
        .then(response => response.json())
        .then(data => this.currentPokemon = data);
  },
  methods:{
    searchPokemon() {
        fetch(`https://pokeapi.co/api/v2/pokemon/${this.lower}`)
            .then(response => response.json())
            .then(data => this.currentPokemon = data);
     
    }
  },
  computed: {
      moves() {
          return this.currentPokemon.moves
      },
      abilities(){
          return this.currentPokemon.abilities
      },
      lower () {
          return this.pokemonName.toLowerCase()
      }
  }
}
</script>

<style>

</style>

