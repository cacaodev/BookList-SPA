<template>
  <div>
    <h2>Catálogo de Libros - Editorial Nova</h2>

    <form @submit.prevent="add" class="form">
      <input v-model="nuevo.titulo" placeholder="Título" @keyup.enter="add" />
      <input v-model="nuevo.autor" placeholder="Autor" />

      <select v-model="nuevo.categoria">
        <option value="" disabled>Seleccione Categoría</option>
        <option value="Ficción">Ficción</option>
        <option value="Ensayo">Ensayo</option>
        <option value="Romance">Romance</option>
      </select>

      <textarea
        v-model="nuevo.resumen"
        placeholder="Resumen del libro"
      ></textarea>

      <button v-show="nuevo.titulo.length > 0" type="submit">
        Agregar Libro
      </button>
    </form>

    <div v-if="nuevo.titulo || nuevo.autor" class="preview">
      <p>
        <strong>Escribiendo:</strong> {{ nuevo.titulo }} - {{ nuevo.categoria }}
      </p>
    </div>

    <hr />

    <div v-if="libros.length > 0">
      <button @click.once="notificar">
        Confirmar revisión de lista (Solo una vez)
      </button>

      <Libro
        v-for="(l, i) in libros"
        :key="i"
        :titulo="l.titulo"
        :autor="l.autor"
        :categoria="l.categoria"
        @eliminar="libros.splice(i, 1)"
      >
        <router-link :to="{ name: 'detalle', params: { id: i } }"
          >Ver Detalles</router-link
        >
      </Libro>
    </div>

    <p v-else>No hay libros disponibles.</p>
  </div>
</template>

<script>
import Libro from "../components/Libro.vue";

export default {
  components: { Libro },
  data() {
    return {
      nuevo: {
        titulo: "",
        autor: "",
        categoria: "",
        resumen: "",
      },
      libros: [
        {
          titulo: "Crepúsculo",
          autor: "Stephenie Meyer",
          categoria: "Romance",
        },
      ],
    };
  },
  methods: {
    add() {
      if (this.nuevo.titulo && this.nuevo.autor) {
        this.libros.push({ ...this.nuevo });
        this.nuevo = { titulo: "", autor: "", categoria: "", resumen: "" };
      }
    },
    notificar() {
      alert("Lista revisada con éxito.");
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 300px;
  margin-bottom: 20px;
}
.preview {
  font-style: italic;
  color: #666;
  margin-bottom: 10px;
}
textarea {
  height: 50px;
  resize: none;
}
button {
  cursor: pointer;
}
</style>
