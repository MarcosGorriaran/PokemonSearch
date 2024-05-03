<template>
 <!-- Código HTML -->
 <h2>Favourite List</h2>
 <template >
  {{ console.log(this.list,"item") }}
    <div v-for="{item,index} in this.list" v-bind:key="index">
      <h3>{{console.log(item,index)}}</h3>
        <img v-bind:src="item.sprites.front_default" v-bind:alt=item.name />
    </div>
 </template>

</template>
   <script>
    //Defincion de componente estilo Option API Vue2+ y Vue3
    export default {
      // Establece un nombre al componente. De lo contrario aparece como "Anónimo" en DevTools.
      name: "ShowFavouriteList",
      // Lista de atributos (props) aceptados desde el componente padre.
      props: {
         list: Array
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
      },
    };
   </script>
   <style>/* Estilos CSS */</style>