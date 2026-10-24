<script setup lang="ts">
    import HeaderComp from '~/components/HeaderComp.vue';
    import FooterComp from '~/components/FooterComp.vue'; 
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
