<script setup lang="ts">
interface Trabajo {
  titulo: string;
  descripcion: string;
  imagen: string;
}
defineProps<{
  homeTrabajos: Trabajo[];
}>()

</script>
<template>
  <article>
    <ul>
      <li v-for="trabajo in homeTrabajos" :key="trabajo.titulo">
        <h3>{{ trabajo.titulo }}</h3>
        <p>{{ trabajo.descripcion }}</p>
        <img :src="trabajo.imagen" :alt="trabajo.titulo" />
      </li>
    </ul>
  </article>
</template>
