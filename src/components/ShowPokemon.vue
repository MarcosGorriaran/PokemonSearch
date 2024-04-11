<template>
 <!-- Código HTML -->
 <div id="base-component"><nombre-componente></nombre-componente></div>
</template>
<script>
 //Defincion de componente estilo Option API Vue2+ y Vue3
 export default {
   // Establece un nombre al componente. De lo contrario aparece como "Anónimo" en DevTools.
   name: "base-component",
   component: { NombreComponente, }, // Lista de los componentes que se usan en el template
   // Lista de atributos (props) aceptados desde el componente padre.
   props: {
      pokemonName: Object
   },
   // Función que devuelve un  con las variables del componente Vue.
   data() {
     return {
        pokemonAPIURL: "https://pokeapi.co/api/v2/pokemon/",
     };
   },
   // Lista de funciones que se ejecutarán cuando se acceda a la propiedad en cuestión.
   computed: {},
   // Lista de funciones (métodos) disponibles en el componente Vue.
   methods: {},
 };
</script>
<style>/* Estilos CSS */</style>