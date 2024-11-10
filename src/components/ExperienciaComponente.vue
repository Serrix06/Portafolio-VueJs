<template>
  <div class="card">
      <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
      <p class="fecha">{{ fecha }}</p>
      <ul class="listado">
          <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
              <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
              <p>{{ experiencia.parrafo }}</p>
          </li>
      </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Definimos las propiedades del componente
const titulo = ref('Experiencia'); // Puedes cambiar esto a lo que necesites
const fecha = ref('Junio 2024'); // Cambia la fecha según sea necesario

// Lista de experiencias
const experiencias = ref([
  {
      id: 1,
      src: '/src/assets/configuracion.svg',
      parrafo: 'Desarrolle un arcade en PSeint con sus repectivas animaciones'
  },
]);
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  padding: 2rem;
  background-color: rgb(28, 41, 52);
  border-radius: 15px;
}

.titulo {
  font-size: 1.5rem;
  color: coral;
}

.fecha {
  font-size: 1rem;
  color: burlywood;
  margin-bottom: 1rem;
}

.listado {
  display: flex;
  flex-direction: column;
}

.item {
  align-items: center;
  display: flex;
  padding: 1rem;
  gap: 1.5rem;
}

.imagen-svg {
  width: 45px; /* Tamaño fijo para la imagen */
}
</style>
