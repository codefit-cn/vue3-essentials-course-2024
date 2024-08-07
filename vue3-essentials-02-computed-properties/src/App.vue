<script lang="ts">
import { computed, defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const count = ref(18)

    const buttonStatus = computed<{ text: string; disabled: boolean }>(() => {
      return {
        text: count.value >= 20 ? '可以参加' : '不够金币，不可以参加',
        disabled: count.value < 20
      }
    })
    function increase() {
      count.value++
    }

    return {
      count,
      increase,
      buttonStatus
    }
  }
})
</script>

<template>
  <main>
    <h1>金币：{{ count }}</h1>
    <button @click="increase">增加金币</button>
    <button :disabled="buttonStatus.disabled">{{ buttonStatus.text }}</button>
    <p>"Hello, Vue.js 3.x 必修课｜2024 By CodeFit"</p>
  </main>
</template>