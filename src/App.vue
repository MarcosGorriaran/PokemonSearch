<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <AskPokemon @sendPokemon="RetrivePokemon"/>
  <p>{{ pokemon.name }}</p>
</template>

<script>
import AskPokemon from './components/AskPokemon.vue';

export default {
  name: 'App',
  components: {
    AskPokemon
},
data() {
  return {
    pokemon: Object
  }
},
methods: {
  RetrivePokemon(payload) {
    console.log(payload);
    this.pokemon = payload
  }
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
