<template>
  <div>

  </div>
</template>

<script>
import { reactive, readonly, toRaw } from 'vue'
export default {
  setup () {
    const foo = {count: 0}
    const reactiveFoo = reactive(foo)
    const copyFoo = readonly(reactiveFoo)
    console.log(toRaw(reactiveFoo) === foo) // true
    console.log(toRaw(copyFoo) === foo) // true
    console.log(toRaw(copyFoo)) // {count: 0}
    console.log(toRaw('diqiu')) // diqiu
    return {}
  }
}
</script>
