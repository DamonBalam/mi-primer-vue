<script setup>
import {ref } from 'vue'

const name = "Arturo Saldivar";
const counter = ref(0);

// método
const increment = () => {
  console.log('aumentar contador');
  counter.value++;
}

</script>

<template>
<h1>Hola {{ name.toUpperCase() }}</h1>
<h2>{{ counter }}</h2>
<button @click="increment">Aumentar</button>
</template>

<style scoped>
h1{
  color: red;
}
</style>
