<script lang="ts">
import { defineComponent, reactive, ref } from "vue";

export default defineComponent({
  name: 'App',
  setup() {
    // 使用 ref() 的部分
    const count = ref(0)

    function increase() {
      count.value++
    }

    // 新增：使用的 reactive() 部分
    const state = reactive({
      reactiveCount: 0,
      message: "Hello, Vue.js 3.x 必修课｜2024 By CodeFit"
    })

    function increaseReactive() {
      state.reactiveCount++
    }

    return {
      // ref() 相关
      count,
      increase,
      // reactive() 相关
      state,
      increaseReactive
    }
  }
})
</script>

<template>
  <main>
    <h1>使用 ref() </h1>
    <h2>{{ count }}</h2>
    <button @click="increase">Increase</button>

    <h1>使用 reactive() </h1>
    <h2>{{ state.reactiveCount }}</h2>
    <button @click="increaseReactive">increaseReactive</button>
    <p>{{ state.message }}</p>
  </main>
</template>

<!-- <style scoped>
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
</style> -->