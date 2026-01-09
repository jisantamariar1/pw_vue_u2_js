<template>
  <div>
    <PokemonImagen :pokemonId="pokemonGanador" />
    <PokemonOpciones @seleccionado="evaluarGanador($event)" :listaPokemons="pokemonArr" />
  </div>

</template>

<script>
import PokemonImagen from '@/components/PokemonImagen.vue';
import PokemonOpciones from '@/components/PokemonOpciones.vue';
import { obtenerVectorPokemonFacade } from '@/clients/PokemonClient.js';
import { obtenerAleatorioFachada } from '@/clients/PokemonClient.js';
export default {
  data() {
    return {
      pokemonArr: [],
      pokemonGanador: null,
    }
  },
  mounted() {
    console.log("componente PokemonView montado");
    this.iniciarJuego();


  },
  components: {
    PokemonImagen,
    PokemonOpciones
  },
  methods: {
    async iniciarJuego() {
      this.pokemonArr = await obtenerVectorPokemonFacade();

      const idAleatorio = obtenerAleatorioFachada(0, 3);
      this.pokemonGanador = this.pokemonArr[idAleatorio].id;



    },
    evaluarGanador(idGanador) {
      console.log('valor recibido desde padre')
      console.log(idGanador);
      if (idGanador === this.pokemonGanador) {
        console.log('¡Has ganado!');
      } else {
        console.log('¡Has perdido! Inténtalo de nuevo.');
      }

    },

  },


};
</script>

<style></style>