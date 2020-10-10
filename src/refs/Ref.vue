<template>
  <button @click="add">+</button>
  <button @click="reduce">-</button>
  {{count}}
</template>

<script>
import { ref } from 'vue'
export default {
  setup () {
    const count = ref(0)
    console.log(count)
    const reduce = () => {
      count.value--
    }
    const add = () => {
      count.value++
    }
    return {
      reduce,
      add,
      count
    }
  }
}
</script>