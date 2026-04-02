<template>
  <div class="detalle">
    <h2>Detalle del Libro</h2>
    <p>Estás viendo la información detallada del libro con ID: <strong>{{ id }}</strong></p>
    <router-link to="/libros">Volver al catálogo</router-link>
  </div>
</template>

<script>
export default {
  props: ['id']
}
</script>

<style scoped>
.detalle { padding: 20px; border: 1px solid #42b983; border-radius: 8px; }
</style>