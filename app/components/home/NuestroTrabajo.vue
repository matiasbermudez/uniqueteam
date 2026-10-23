<script setup lang="ts">
import { homeTrabajos } from "@/assets/constants";
import CardTrabajo from "./CardTrabajo.vue";
</script>
<template>
  <article
    class=" bg-[#090a0b] px-[var(--padding-x)] pt-16 pb-16 text-white"
  >
    <div class="pb-[4.9rem] text-start border-b border-unique-gris">
      <h2 class="font-extrabold text-[1rem] mb-[1rem]">NUESTRO TRABAJO</h2>
      <p>Proyectos que ya pusimos en funcionamiento</p>
      <p>durante el proceso del año viciesto</p>
      <p>correspondiente a genesis saturno.</p>
    </div>
    <CardTrabajo :homeTrabajos="homeTrabajos" />
  </article>
</template>
