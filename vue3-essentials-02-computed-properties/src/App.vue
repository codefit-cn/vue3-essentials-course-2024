<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const count = ref(18)
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
    <h1>金币：{{ count }}</h1>
    <button @click="increase">增加金币</button>
    <button :disabled="count < 20">{{ count >= 20 ? '可以参加' : '不够金币，不可以参加' }}</button>
    <p>"Hello, Vue.js 3.x 必修课｜2024 By CodeFit"</p>
  </main>
</template>