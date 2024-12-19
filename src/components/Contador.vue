<template>
  <h2>{{ titulo }}</h2>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <div>
    <button v-on:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: 10,
      titulo: "Contador",
    };
  },

  methods: {
    calcularCuadrado() {
      console.log("Método calcularCuadrado");
      return this.numero * this.numero;
    },
    incrementar() {
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },

  computed: {
    calcularCuadradoComputado() {
      console.log("Método calcularCuadradoComputado");
      return this.numero * this.numero;
    },
  },
};
</script>

<style>

button {
  background: #64b687;
  border-radius: 5px;
  padding: 10px 10px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
  width: 100px;

}

button:hover {
  background: #001a46;
}


</style>