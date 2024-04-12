<template>
<!-- Código HTML -->
    <div>
        <form @submit.prevent>
            <label>Provide a pokemon name</label>
            <input type="text" v-model="pokemonName" />
            <template v-if="loading">
                <img src="LoadingImage.gif" id="loadingImg"/>
            </template>
            
            <button @click="getPokemon">Get Pokémon</button>
            <template v-if="error">
                <p>{{ errorMessage }}</p>
            </template>
        </form>
    </div>
</template>
<script>
//Defincion de componente estilo Option API Vue2+ y Vue3
import { PokemonClient} from 'pokenode-ts';
export default {
    // Establece un nombre al componente. De lo contrario aparece como "Anónimo" en DevTools.
    name: "AskPokemon", // Lista de los componentes que se usan en el template
    // Lista de atributos (props) aceptados desde el componente padre.
    props: {},
    // Función que devuelve un  con las variables del componente Vue.
    data() {
        return {
            error: false,
            loading: false,
            errorMessage: "",
            pokemonName: "",
            pokedex: new PokemonClient()
        };
    },
    // Lista de funciones que se ejecutarán cuando se acceda a la propiedad en cuestión.
    computed: {},
    // Lista de funciones (métodos) disponibles en el componente Vue.
    methods: {
        getPokemon() {
            this.error = false;
            this.loading = true;
            this.pokedex.getPokemonByName(this.pokemonName).then((pokemon) => {
                this.$emit("sendPokemon", pokemon);
                this.loading = false;
            }).catch((error) => {
                this.loading = false;
                this.error = true;
                this.errorMessage = error.message;
            });
    }
    },
};
</script>
<style>
    #loadingImg{
        width: 50px;
        height: 50px;
    }
</style>
   