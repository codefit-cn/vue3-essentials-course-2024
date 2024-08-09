<script lang="ts">
import { defineComponent, ref, watch } from 'vue';

export default defineComponent({
  name: 'App',

  setup() {
    const count = ref(18)

    watch(count, (newValue, oldValue) => {
      console.log(`Count changed from ${oldValue} to ${newValue}`)
      document.title = `当前点击次数：${newValue}`
    })

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
  <div>
    <h1>监听点击次数：{{ count }}</h1>
    <button @click="increase">增加</button>
    <p>"Hello, Vue.js 3.x 必修课｜2024 By CodeFit"</p>
  </div>
</template>
