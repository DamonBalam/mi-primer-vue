<script setup>
const name = "Arturo Saldivar";


// método
const handleClick = (message) => {
  console.log(message);
}

</script>

<template>
<h1>Hola {{ name.toUpperCase() }}</h1>
<button @click.right="handleClick('Texto Right')">Activame right</button>
<button @click.middle="handleClick('Texto Middle')">Activame middle</button>
<button @click="handleClick('Texto Left')">Activame left</button>
</template>

<style scoped>
h1{
  color: red;
}
</style>
