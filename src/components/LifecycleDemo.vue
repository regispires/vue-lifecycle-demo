<template>
  <div>
    <p>Contador: {{ state.count }}</p>
    <p>Dobro: {{ doubleCount }}</p>
    <button @click="increment">Incrementar</button>
  </div>
</template>

// Na Options API havia os eventos beforeCreate e created, que nao existem na Composition API.
// Na Composition API, o bloco setup() é chamado após beforeCreate e created, 
// tornando esses hooks desnecessários. 
<script setup>
import {
  reactive,
  computed,
  watch,
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

// Watch para observar mudanças em state.count
// watch(
//   () => state.count,
//   (newVal, oldVal) => {
//     console.log(`watch: count mudou de ${oldVal} para ${newVal}`)
//   }
// )

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