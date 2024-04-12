<template>
 <!-- Código HTML -->
 <h2>Favourite List</h2>
 <template v-for="{item,index} in list" :key="index">
    <div>
        {{ hello(index)}}
        <img v-bind:src="item[index].value.sprites.front_default" v-bind:alt=item[index].value.name />
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
         list: new Set()
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
        hello(element){
            console.log(element);
        }
      },
    };
   </script>
   <style>/* Estilos CSS */</style>