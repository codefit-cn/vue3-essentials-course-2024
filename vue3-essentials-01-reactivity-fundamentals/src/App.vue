<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: 'App',
  setup() {
    const count = ref(0)

    function increase() {
      count.value++
    }
    return {
      count,
      increase
    }
  }
})
</script>

<template>
  <main>
    <h1>{{ count }}</h1>
    <button @click="increase">Increase</button>
  </main>
</template>

<style scoped>
main {
  text-align: center;
  padding: 20px;
}

h1 {
  font-size: 2em;
  margin-bottom: 20px;
}

button {
  font-size: 1em;
  padding: 10px 20px;
  cursor: pointer;
}
</style>