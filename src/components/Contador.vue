<template>
  <h2>{{ encabezado }}: {{ valor2 }}</h2>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  <p>{{ numero }}<sup>2</sup> = {{ calcularCuadradoComputado }}</p>
  
  <div>
    <button @:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>

  <div v-if="esVerdad">
    <h1>FELIZ NAVIDAD</h1>
  </div>

</template>


<!-------------------------------------------------------->

<script>
export default {
  data() {
    return {
      numero: this.valor,
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
  //Primera forma de declarar props
  //props: ['encabezado','valor'],

  //Segunda forma de declarar props
  props: {
    encabezado: String,
    valor: Number,
    valor2: {
      type: Number,
      required: false,
      default: 78,
      validator(value){
        return value <=77;
      }
    },
    esVerdad: {
      type: Boolean,
      required: true,
    },
    arreglo: Array,
    fecha: Date,
    objetoPersona: Object,
    

  },
  



};
</script>


<!-------------------------------------------------------->


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