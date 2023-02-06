<script setup>
import { ref, computed } from 'vue'

const name = "Arturo Saldivar";
const counter = ref(0);
const listaNumeros = ref([])
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

const add = () => {
  listaNumeros.value.push(counter.value);
}

const classCounter = computed(() => {
  if (counter.value === 0) {
    return 'color:peru'
  }
  return counter.value > 0 ? 'color:green' : 'color:red'
})

const validateInput = computed(() => {
  
  const result = listaNumeros.value.filter( item => item === counter.value );

  return result.length === 0 ? true : false;
})

</script>

<template>
  <div class="container mx-auto d-flex flex-column justify-content-center align-items-center mt-5">
    <h1>Hola {{ name }}</h1>
    <h2 :style="classCounter" class="fs-1">{{ counter }}</h2>
    <div>
      <button class="btn btn-success mx-1" @click="increment">Aumentar</button>
      <button class="btn btn-secondary mx-1" @click="reset">Resetear</button>
      <button class="btn btn-danger mx-1" @click="decrement">Disminuir</button>
    </div>
    <button class="btn btn-primary mt-2 px-5" @click="add" :disabled="!validateInput">Agregar número favorito</button>
    <h2 class="mt-5">Numero favoritos:</h2>
    <ul class="list-group">
      <li class="list-group-item text-center" style="width: 200px;" v-for="num in listaNumeros">
        {{ num }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
/* *, *:before, *:after {
	box-sizing: border-box;
	outline: none;
} */
</style>
