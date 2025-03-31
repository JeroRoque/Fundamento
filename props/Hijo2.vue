<script setup>
defineProps({
  edad: Number,
})
</script>

<template>
  <h6>Soy el componente Hijo2</h6>
  <p>{{ edad }}</p>
</template>

<style scoped></style>
