<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import {navLinks} from '~/assets/constants'
const menuAbierto = ref(false)

const scrolled = ref(false)

function handleScroll() {
  scrolled.value = window.scrollY > 20
}

onMounted(() => {
  handleScroll()
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header
    class="sticky top-0 z-50 w-full bg-transparent transition-colors duration-300 py-[0.875rem] flex justify-between items-center"
    :class="scrolled ? 'bg-unique-blanco/95' : 'bg-transparent'" 
    >
    <h1
      class="text-unique-negro font-jakarta font-extrabold text-[1.25rem] leading-[1rem] tracking-normal px-[2.063rem]"
    >
      <span class="text-unique-naranja">U</span>nique<span class="text-unique-naranja">T</span>eam
    </h1>

    <button
      type="button"
      class="flex h-[28px] w-[28px] flex-col items-center justify-center gap-[5px] px-[2.063rem] md:hidden"
      :aria-label="menuAbierto ? 'Cerrar menú' : 'Abrir menú'"
      :aria-expanded="menuAbierto"
      @click="menuAbierto = !menuAbierto"
    >
      <span
        class="block h-[2px] w-[28px] bg-unique-negro transition-transform duration-300 ease-in-out"
        :class="menuAbierto ? 'translate-y-[3.5px] rotate-45' : ''"
      ></span>

      <span
        class="block h-[2px] w-[28px] bg-unique-negro transition-transform duration-300 ease-in-out"
        :class="menuAbierto ? '-translate-y-[3.5px] -rotate-45' : ''"
      ></span>
    </button>

     <!-- Menú mobile -->
    <nav
      v-if="menuAbierto"
      class="absolute left-0 top-full flex w-full flex-col gap-6 bg-unique-blanco/95 px-[var(--padding-x)] py-8 shadow-lg md:hidden"
    >
      <NuxtLink
        v-for="link in navLinks"
        :key="link.href"
        :to="link.href"
        class="font-jakarta font-semibold text-unique-negro transition-colors hover:text-unique-naranja"
        @click="menuAbierto = false"
      >
        {{ link.name }}
      </NuxtLink>
    </nav>

  </header>
</template>
