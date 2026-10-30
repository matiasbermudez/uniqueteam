<script setup lang="ts">
    import HeaderComp from '~/components/layout/HeaderComp.vue';
    import FooterComp from '~/components/layout/FooterComp.vue'; 
</script>
<template>
  <div>
    <HeaderComp />

    <main>
      <slot />
    </main>

    <FooterComp />
  </div>
</template>
