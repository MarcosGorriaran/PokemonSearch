<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <AskPokemon @sendPokemon="RetrivePokemon"/>
  
  <ShowPokemon v-if="IsPokemonSet" @sendFavourite="AddFavourite" :pokemon="pokemon"/>
  <FavouriteList :list="pokemonList"/>
</template>

<script>
import AskPokemon from './components/AskPokemon.vue';
import ShowPokemon from './components/ShowPokemon.vue';
import FavouriteList from './components/FavouriteList.vue';
export default {
  name: 'App',
  components: {
    FavouriteList,
    AskPokemon,
    ShowPokemon,
    
},
data() {
  return {
    pokemon: Object,
    pokemonList: [],
    IsPokemonSet: false
  }
},
methods: {
  RetrivePokemon(payload) {
    this.IsPokemonSet = true;
    console.log(payload);
    this.pokemon = payload
  },
  AddFavourite(payload){
    this.pokemonList.push(payload);
  }
},
computed: {
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input,button{
  border-color: black;
  border-width: 2px;
  border-radius: 5px;
  border-style: solid ;
}
</style>
