<template>
  <button @click="show = !show">
    {{ show ? 'Ocultar' : 'Mostrar' }} Componente
  </button>
  <LifecycleDemo v-if="show" />
</template>

<script setup>
import { ref } from 'vue'
import LifecycleDemo from './components/LifecycleDemo.vue'

const show = ref(true)
</script>
