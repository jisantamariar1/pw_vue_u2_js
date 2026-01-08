<template>
  <div>
    <PokemonImagen :pokemonId="1"/>
    <PokemonOpciones />
  </div>
</template>

<script>
    import PokemonImagen from '@/components/PokemonImagen.vue';
    import PokemonOpciones from '@/components/PokemonOpciones.vue';
export default {
    components: {
        PokemonImagen,
        PokemonOpciones
    },
    methods: {

    }

}
</script>

<style>

</style>