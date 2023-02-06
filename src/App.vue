<script setup>
import {ref,computed } from 'vue'

const name = "Arturo Saldivar";
const counter = ref(0);

// método
const increment = () => {
  counter.value++;
}
const reset = () => {
  counter.value = 0;
}

const decrement = () => {
  counter.value--;
}

const classCounter = computed( ()=> {

  if (counter.value === 0) {
    return 'color:peru'
  }

  return counter.value > 0 ? 'color:green' : 'color:red'
})

</script>

<template>
<h1>Hola {{ name.toUpperCase() }}</h1>
<h2 :style="classCounter">{{ counter }}</h2>
<button @click="increment">Aumentar</button>
<button @click="reset">Reset</button>
<button @click="decrement">Disminuir</button>
</template>

<style scoped>
h1{
  color: red;
}
</style>
