<script setup>
const props = defineProps({
  resultado: Number,
});
</script>

<template>
  <section class="px-5 mb-5">
    <div class="row mt-3">
      <div class="col text-center">
        <p class="fs-4">Resultado: {{ props.resultado }}</p>
      </div>
    </div>
  </section>
</template>
