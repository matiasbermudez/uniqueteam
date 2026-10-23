<script setup lang="ts">
interface Trabajo {
  titulo: string;
  descripcion: string;
  imagen: string;
  link: string;
  tecnologias: string[];
}
defineProps<{
  homeTrabajos: Trabajo[];
}>()

</script>
<template>
  <article class="py-6">
    <ul class="flex flex-col gap-10">
      <li v-for="trabajo in homeTrabajos" :key="trabajo.titulo" class="flex flex-col gap-4 border-b border-unique-gris pb-4">
        <h3 class="text-[0.875rem]">{{ trabajo.titulo }}</h3>
        <img :src="trabajo.imagen" :alt="trabajo.titulo" class="max-h-[4rem] max-w-[5rem] " />
        <p class="text-[0.75rem]">{{ trabajo.descripcion }}</p>
        
        <ul class="flex gap-2 text-unique-gris text-[0.75rem]">
          <li v-for="tecnologia in trabajo.tecnologias" :key="tecnologia">{{ tecnologia }}</li>
        </ul>
        <NuxtLink :to="trabajo.link" class="text-unique-naranja text-end hover:text-unique-gris text-[0.75rem]">Ver Proyecto</NuxtLink>
        
      </li>
    </ul>
  </article>
</template>
