<template>
  <section class="section">
    <h3>Counter: {{ counter }}</h3>
    <h3>Square: {{ squareCounter }}</h3>
    <h4>{{ text }}</h4>
    <div>
      <button class="btn" @click="increment">+1</button>
      <button class="btn" @click="decrement">-1</button>
    </div>
  </section>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue'

export default defineComponent({
  props: {
    // value: Number, --> seria opcional
    // value: { type: Number, default: 10 } // tambien podria ponerle un valor por defecto si quiero mantenerlo en opcional
    value: { type: Number, required: true }, // para hacerlo requerido
    text: { type: String, required: true }
  },
  setup(props) {
    const counter1 = ref(props.value)
    const squareCounter = computed(() => counter.value * counter.value)
    const incr = () => counter.value++
    const decr = () => counter.value--

    return { counter: counter1, squareCounter, increment: incr, decrement, decr }
  }
})
</script>

<style scoped>
.btn {
  @apply bg-green-800 text-white font-bold py-2 px-4 rounded mr-2;
}
</style>
