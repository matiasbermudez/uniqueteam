<script setup lang="ts">
    import HeaderComp from '~/components/HeaderComp.vue';
</script>
<template>
  <div>
    <HeaderComp />

    <main>
      <slot />
    </main>

    <footer>
      <!-- Tu footer -->
    </footer>
  </div>
</template>
