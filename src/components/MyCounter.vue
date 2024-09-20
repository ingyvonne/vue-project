<template>
  <section class="section">
    <h3>Counter: {{ counter }}</h3>
    <h3>Square: {{ squareCounter }}</h3>
    <h4>{{ text }}</h4>
    <div>
      <!-- <button @click="counter++">+1</button> -->
      <button class="btn" @click="increment">+1</button>
      <!-- <button @click="counter--">-1</button> -->
      <button class="btn" @click="decrement">-1</button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'
interface Props {
  value: number
  text: string
}
const props = defineProps<Props>()
// ESTO ES LO MISMO QUE LO DE ARRIBA
// const props = defineProps({
//   value: { type: Number, required: true }
// })
const counter = ref(props.value)
const squareCounter = computed(() => counter.value * counter.value)
const increment = () => counter.value++
const decrement = () => counter.value--
</script>

<style scoped>
.btn {
  @apply bg-green-800 text-white font-bold py-2 px-4 rounded mr-2;
}
</style>
