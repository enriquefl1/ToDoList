<template>
  <div id="app">
    <h1>{{ message }}</h1>
    <input v-model="valorTarea" />
    <button @click="agregaTarea">Agregar</button>
    <ul>
      <li v-for="(nodo, i) in nodoTarea" :key="i">
        {{ nodo }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "Ingrese una tarea en el input",
      valorTarea: "",
      nodoTarea: [],
    };
  },
  methods: {
    agregaTarea() {
      this.valorTarea === ""
        ? alert("No puedes dejar el campo vacio")
        : this.nodoTarea.push(this.valorTarea);
      this.valorTarea = "";
      console.log(this.nodoTarea);
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
