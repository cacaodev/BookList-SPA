<template>
  <div id="app">
    <h1>Bienvenido, {{ usuario }}</h1>

    <nav>
      <router-link to="/">Inicio</router-link> |
      <router-link to="/libros">Lista de Libros</router-link>
    </nav>

    <hr />

    <div>
      <h3>Panel de Control</h3>
      <p>Contador de clics: {{ contador }}</p>
      <button @click="incrementar">Aumentar</button>
    </div>

    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      usuario: "Cami",
      contador: 0,
    };
  },
  methods: {
    incrementar() {
      this.contador++;
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  padding: 20px;
  line-height: 1.6;
}
nav {
  margin-bottom: 20px;
}
button {
  cursor: pointer;
  padding: 5px 10px;
}
</style>
