<template>
 <!-- Código HTML -->
 <div>
   <h1>{{pokemon.name}}</h1>
   <img :src="pokemon.sprites.front_default" :alt=pokemon.name />
   <p>Weight: {{pokemon.weight}}</p>
   <p>Height: {{pokemon.height}}</p>
   <p>Base Experience: {{pokemon.base_experience}}</p>
   <button @click="SendFavourite">Add Favourite</button>
 </div>
</template>
<script>
 //Defincion de componente estilo Option API Vue2+ y Vue3
 export default {
   // Establece un nombre al componente. De lo contrario aparece como "Anónimo" en DevTools.
   name: "ShowPokemon",
   // Lista de atributos (props) aceptados desde el componente padre.
   props: {
      pokemon: Object
   },
   // Función que devuelve un  con las variables del componente Vue.
   data() {
     return {
     };
   },
   // Lista de funciones que se ejecutarán cuando se acceda a la propiedad en cuestión.
   computed: {
      
   },
   // Lista de funciones (métodos) disponibles en el componente Vue.
   methods: {
    SendFavourite(){
      this.$emit("sendFavourite", this.pokemon);
    },
    RemoveFavourite(){
      this.$emit("removeFavourite", this.pokemon);
    }
   },
 };
</script>
<style>/* Estilos CSS */</style>