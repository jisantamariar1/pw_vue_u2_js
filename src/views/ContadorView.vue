<template>
  <div>
    <Contador tit2="Contador 1" v-bind:inicio="20" :mostrar="true"/>
    <Contador tit2="Contador 2"  :inicio="4" :mostrar="false"/>
  </div>
</template>

<script>
import Contador from '../components/Contador.vue'
export default {
    components:{
        Contador,
    },


};
</script>

<style>

</style>