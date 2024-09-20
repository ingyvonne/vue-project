<template>
  <h1>Mi primera App</h1>
  <h1 className="text-3xl font-bold underline">Hello world!</h1>
  <hr />
  <MyCounter :value="5" text="Hola Mundo" />
  <MyCounterScript :value="10" text="Hello World" />
  <MyCounterTraditional :value="5" />
</template>

<script setup lang="ts">
import MyCounterTraditional from './components/my-counter-traditional/MyCounterTraditional.vue'
import MyCounter from './components/MyCounter.vue'
import MyCounterScript from './components/MyCounterScript.vue'
</script>

<style scoped></style>
