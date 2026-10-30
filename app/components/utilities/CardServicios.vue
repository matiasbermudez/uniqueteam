
<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  isOpen: {
    type: Boolean,
    default: false,
  },
})
</script>
<template>
  <article class="card-servicios"
    :class="isOpen ? 'is-open' : 'is-closed'">
    <h2 class=" font-jakarta font-bold text-[1.25rem] leading-[1.5rem]">
      {{ title }}
    </h2>
    <p class="font-jakarta font-medium text-[1rem] leading-[1.5rem] mt-[2.93rem] card-servicios__description">
      {{ description }}
    </p>
  </article>
</template>

<style scoped>
.card-servicios {
  box-sizing: border-box;
  overflow: hidden;
  padding: 32px 24px;
  border-radius: 24px;
  height: 100px;
  transition:
    height 0.5s ease,
    background-color 0.4s ease,
    color 0.4s ease;
  
}

.card-servicios h2 {
  margin: 0;
  font-size: clamp(28px, 4vw, 36px);
  line-height: 1.05;
  letter-spacing: -0.04em;
  font-weight: 650;
}

.card-servicios__description {
  margin: 42px 0 0;
  font-size: 20px;
  line-height: 1.25;

  transition:
    opacity 0.3s ease,
    transform 0.3s ease;
}

/* ESTADO CERRADO */
.card-servicios.is-closed {
  height: 100px;
  background: #f0f0f0;
  color: #080808;
  display: flex;
  align-items: center;
}

.card-servicios.is-closed .card-servicios__description {
  opacity: 0;
  transform: translateY(10px);
  margin-top: 0;
}

/* ESTADO ABIERTO */
.card-servicios.is-open {
   height: 414px;
  background-color: #111213;
  color: #fff;
}

.card-servicios.is-open .card-servicios__description {
  opacity: 1;
  transform: translateY(0);
}
</style>