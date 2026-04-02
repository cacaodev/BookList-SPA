<template>
  <div class="libro-card">
    <h3>{{ titulo }}</h3>
    <p><strong>Autor:</strong> {{ autor }}</p>
    <p><strong>Categoría:</strong> {{ categoria }}</p>
    
    <div class="acciones">
      <slot></slot>
      <button @click="$emit('eliminar')">Eliminar</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['titulo', 'autor', 'categoria']
}
</script>

<style scoped>
.libro-card {
  border: 1px solid #42b983;
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 8px;
  background-color: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.acciones {
  margin-top: 10px;
  display: flex;
  gap: 15px;
  align-items: center;
}

button {
  background-color: #ff4d4d;
  color: white;
  border: none;
  padding: 5px 12px;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #ff1a1a;
}
</style>