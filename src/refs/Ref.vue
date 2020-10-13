<template>
  <button @click="add">+</button>
  <button @click="reduce">-</button>
  {{count}}
</template>

<script>
import { ref, unref } from 'vue'
export default {
  setup () {
    const count = ref(0)
    const num = 12
    console.log(count) // RefImpl {_rawValue: 0, _shallow: false, __v_isRef: true, _value: 0}
    console.log(unref(count)) // 0
    console.log(unref(num)) //
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