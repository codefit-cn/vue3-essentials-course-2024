<script lang="ts">
import { defineComponent, reactive, ref } from "vue";

// 为 reactive 对象定义一个接口
interface State {
  reactiveCount: number;
  message: string;
}

export default defineComponent({
  name: 'App',
  setup() {
    // 使用 ref() 的部分，添加类型注解
    const count = ref<string | number>(0)
    function increase() {
      // 使用类型守卫
      if (typeof count.value === 'number') {
        count.value++
      }
    }

    // 使用 reactive() 的部分，添加类型注解
    const state = reactive<State>({
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