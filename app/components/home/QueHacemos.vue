<script setup lang="ts">
import { homeServicios } from "~/assets/constants";
import CardServicios from "./CardServicios.vue";
import { ref, onMounted, onUnmounted } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

const activeIndex = ref(0);
const sectionRef = ref<HTMLElement | null>(null);
onMounted(() => {
  gsap.registerPlugin(ScrollTrigger);

  ScrollTrigger.create({
    trigger: sectionRef.value,
    start: "top top",
    end: `+=${homeServicios.length * 500}`,
    pin: true,
    scrub: true,

    onUpdate: (self) => {
      const index = Math.round(
        self.progress * (homeServicios.length - 1)
      );

      activeIndex.value = index;
    },
  });
});
</script>

<template>
  <section
    ref="sectionRef"
    class="relative z-10 -mt-8 rounded-t-[2rem] bg-unique-blanco px-[var(--padding-x)] py-16"
  >
    <h2 class="font-jakarta text-[1rem] font-extrabold text-unique-negro">
      QUÉ HACEMOS
    </h2>

    <div class="mt-5 font-jakarta font-medium text-[0.90rem] text-unique-negro">
      <p>Combinamos diseño, desarrollo y tecnología</p>
      <p>para construir productos útiles, funcionales y</p>
      <p>preparados para evolucionar.</p>
    </div>
    <ul class="servicios-lista !mt-[3.18rem]">
      <li v-for="(servicio, index) in homeServicios" :key="index">
        <CardServicios
          :title="servicio.title"
          :description="servicio.description"
          :isOpen="activeIndex === index"
        />
      </li>
    </ul>
  </section>
</template>
