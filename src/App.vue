<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Contador
    encabezado="Primero"
    :valor="calcular(1, 3)"
    :esVerdad="muestra1"
    :valor2="2"
  />
  <hr />
  <Contador
    encabezado="Segundo"
    v-bind:valor="calcular(8, 2)"
    :esVerdad="muestra2"
  />
  
  <hr />  
  <button @click="cambiar(1)">Cambiar Primero</button>
  <button @click="cambiar(2)">Cambiar Segundo</button>
</template>

<script>
import Contador from "./components/Contador.vue";
export default {
  name: "App",
  components: {
    Contador,
  },

  data() {
    return {
      muestra1: true,
      muestra2: false,
    };
  },

  methods: {
    calcular(a, b) {
      return a + b;
    },
    cambiar(valor) {
      if (valor === 1) {
        this.muestra1 = !this.muestra1;
      } else {
        this.muestra2 = !this.muestra2;
      }
    },
  },
};
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
</style>
