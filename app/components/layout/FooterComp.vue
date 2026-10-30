<script setup lang="ts">
import BotonHablemos from "~/components/utilities/BotonHablemos.vue";
import { socialLinks } from "~/assets/constants";
</script>
<template>
  <footer
    class="w-full bg-unique-negro text-unique-blanco text-start px-[2.063rem] pt-[9rem] flex flex-col gap-[4rem] 
                  md:flex-row md:justify-between md:gap-[9rem] md:px-[8.313rem] md:pb-[14rem]"
  >
    <article>
      <h3 class="mb-[1.5rem]">Explorar</h3>
      <div class="footer-links-info">
        <NuxtLink to="/proyectos">Proyectos</NuxtLink>
        <NuxtLink to="/servicios">Servicios</NuxtLink>
        <NuxtLink to="/estudio">Estudio</NuxtLink>
        <NuxtLink to="/ejemplos">Ejemplos</NuxtLink>
      </div>
    </article>
    <article>
      <h3 class="mb-[1.5rem]">Estudio</h3>
      <div class="footer-links-info">
        <p>Unique Team</p>
        <p>Diseñamos</p>
        <p>Desarrollamos</p>
        <p>Mejoramos</p>
      </div>
    </article>
    <article>
      <h3 class="mb-[1.5rem]">Servicios</h3>
      <div class="footer-links-info">
        <p>Diseño UX/UI</p>
        <p>Desarrollo</p>
        <p>Soluciones IT</p>
        <p>SEO</p>
        <p>Redes y contenido</p>
        <p>Post-producto</p>
        <p>Impulso Digital</p>
      </div>
    </article>

    <article class="flex flex-col gap-[4rem] md:max-w-[22rem]">
      <div class="">
        <h3 class="mb-[1.5rem]">Mejorá</h3>
        <p class="footer-links-info mb-[3.375rem]">
          UniqueTeam conviene porque reúne diseño, desarrollo y tecnología en un
          mismo proyecto, evitando soluciones desconectadas entre sí. La idea es
          acompañar cada trabajo desde la planificación y la experiencia visual
          hasta la programación y puesta en funcionamiento, buscando que el
          resultado sea útil, funcional, escalable.
        </p>
        <BotonHablemos />
      </div>

      <div class="flex justify-between md:max-w-[70%]">
        <NuxtLink v-for="link in socialLinks" :key="link.nombre" :to="link.url">
          <img
            :src="`/${link.imagen}.png`"
            :alt="link.nombre"
            class="max-w-[2.5rem] md:max-w-[1.875rem]"
          />
        </NuxtLink>
      </div>
    </article>
  </footer>
</template>
