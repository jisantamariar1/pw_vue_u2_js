<template>
  <div>
    <h1>{{ tit2 }}</h1>
    <p>{{ numero }}<sup>2</sup>={{ calculaCuadrado}}</p>
    <p>{{ numero }}<sup>2</sup>={{ calculaCuadrado}}</p>
    <p>{{ numero }}<sup>2</sup>={{ calculaCuadrado }}</p>
    <p>{{ numero }}<sup>3</sup>={{calculaCubo}}</p>
    <p>{{ numero }}<sup>3</sup>={{obtenercubo()}}</p>
  </div>
  <div>
      <button v-on:click="incrementar()">+1</button>
      <button v-on:click="decrementar()">-1</button>
      <button v-if="mostrar">prueba</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      numero:this.inicio,
      titulo: "Contador",

    };
  }, 
  methods:{
    obtenercuadrado(){
      console.log("Entro a obtener cuadrado");
      return this.numero*this.numero;
    },
    obtenercubo(){
      return this.numero*this.numero*this.numero;
    },
    incrementar(){
      console.log(this.tit2);
      return this.numero++;
    },
    decrementar(){
      return this.numero--;
    }
  },
  computed:{
    calculaCuadrado(){
      console.log("Entro a propiedad computada");
      return this.numero*this.numero;
    },
    calculaCubo(){
      return this.numero*this.numero*this.numero;
    }
  },
  /*props:['tit2','inicio','mostrar']*/
  /*Declaracion especifico*/
  props:{
    tit2:String,
    /*Da opcion a configurar varias cosas en el props */
    inicio:{
      type:Number,
      default:99,
      validator(value){
        return value>10;
      }
    },
    mostrar:Boolean
  }
  /*Declaraciones*/
  /*String, Number, Array, Object, Date, Function, (enteros grandes) BigInt*/
  
};
</script>

<style>

</style>