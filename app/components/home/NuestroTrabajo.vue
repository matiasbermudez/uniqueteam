<script setup lang="ts">
import { homeTrabajos } from "@/assets/constants";
import CardTrabajo from "./CardTrabajo.vue";
</script>
<template>
  <article
    class="relative z-1 md:-mt-26 md:pt-[18rem] bg-[#090a0b] px-[var(--padding-x)] pt-16 pb-16 text-white md:px-[8.2rem] md:pb-[14rem] "
  >
    <div class="pb-[4.9rem] text-start border-b border-unique-gris md:flex md:justify-between ">
      <h2 class="font-extrabold text-[1rem] mb-[1rem] ">NUESTRO TRABAJO</h2>
      <p class="md:text-[1.5rem]">Proyectos que ya pusimos en funcionamiento</p>
      <p class="md:hidden">durante el proceso del año viciesto</p>
      <p class="md:hidden">correspondiente a genesis saturno.</p>
    </div>
    <CardTrabajo :homeTrabajos="homeTrabajos" />
  </article>
</template>
