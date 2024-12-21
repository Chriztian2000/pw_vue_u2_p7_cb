<template>
  <img
    :src="imagen"
    alt="NO SE PUEDE VER"
  />
  <br />
  <input v-model="pregunta" type="text" placeholder="Hazme una Pregunta" />
  <p>Recuerda que cuando finalice tu pregunta poner un ?</p>
  <h1>{{ pregunta }}</h1>
  <h2>{{ respuesta }}</h2>
</template>

<script>
export default {
  data() {
    return {
      pregunta: "Como te llamas?",
      respuesta: null,
      imagen: "https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif",
    };
  },
  watch: {
    pregunta(value, oldValue) {
      console.log(value);
      console.log(oldValue);
      if (value.includes("?")) {
        //PROGRAMAR LA LLAMADA AL API PARA
        //OBTENER EL SI Y NO CON LA IMAGEN
        console.log("Aqui llamo al API");
        this.llamarAPI();
      }
    },
  },
  methods: {
    async llamarAPI() {
      const data = await fetch("https://yesno.wtf/api").then((resp) => resp.json());
      this.respuesta = data.answer;
      this.imagen = data.image;
      console.log(data);
    },
  },
};
</script>

<style>
</style>