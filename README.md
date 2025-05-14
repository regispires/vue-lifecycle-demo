# Exemplo sobre o ciclo de vida do Vue 3

## Ordem dos eventos
- setup
- onBeforeMount
- computed
- onMounted
---------------------------
- watch
- onBeforeUpdate
- computed
- onUpdated
---------------------------
- onBeforeUnmount
- onUnmounted

Computed é executado apenas quando você acessa seu valor — no template ou em código — e só reexecuta se suas dependências reativas mudarem.


