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
  <article class="py-6  ">
    <ul class="flex flex-col gap-10  ">
      <li v-for="trabajo in homeTrabajos" :key="trabajo.titulo" class="flex flex-col gap-4 border-b border-unique-gris  pb-4 md:flex-row md:justify-between md:items-center md:h-[14rem]">
        <h3 class="text-[0.875rem] md:hidden md: font-medium">{{ trabajo.titulo }}</h3>
        <img :src="trabajo.imagen" :alt="trabajo.titulo" class="max-h-[4rem] max-w-[5rem] md:max-h-[10.5rem] md:max-w-[10.5rem]" />
        <p class="text-[0.75rem] md:text-[1rem] md:flex md:px-[7.813rem] md:text-center ">{{ trabajo.descripcion }}</p>
        
        <ul class="flex gap-2 text-unique-gris text-[0.75rem] md:hidden">
          <li v-for="tecnologia in trabajo.tecnologias" :key="tecnologia">{{ tecnologia }}</li>
        </ul>
        <NuxtLink :to="trabajo.link" class="text-unique-naranja text-end hover:text-unique-gris text-[0.75rem] md:hidden">Ver Proyecto</NuxtLink>
        <NuxtLink :to="trabajo.link" class="bg-unique-naranja text-unique-negro font-bold min-w-[4rem] min-h-[2rem] md:flex md:justify-center md:items-center rounded-4xl text-[0.85rem] hidden">Ver</NuxtLink>
      </li>
    </ul>
  </article>
</template>
