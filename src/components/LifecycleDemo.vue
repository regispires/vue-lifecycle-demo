<template>
  <div>
    <p>Contador: {{ state.count }}</p>
    <p>Dobro: {{ doubleCount }}</p>
    <button @click="increment">Incrementar</button>
  </div>
</template>

<script setup>
import {
  reactive,
  computed,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted
} from 'vue'

console.log('setup() - componente está sendo criado')

const state = reactive({
  count: 0
})

const doubleCount = computed(() => {
  console.log('computed: doubleCount reavaliado')
  return state.count * 2
})

const increment = () => {
  state.count++
}

onBeforeMount(() => {
  console.log('onBeforeMount - antes de montar no DOM')
})

onMounted(() => {
  console.log('onMounted - componente montado no DOM')
})

onBeforeUpdate(() => {
  console.log('onBeforeUpdate - antes da atualização do DOM')
})

onUpdated(() => {
  console.log('onUpdated - após atualização do DOM')
})

onBeforeUnmount(() => {
  console.log('onBeforeUnmount - antes do componente ser desmontado')
})

onUnmounted(() => {
  console.log('onUnmounted - componente desmontado')
})
</script>
