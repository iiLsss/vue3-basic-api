<template>
  <div>

  </div>
</template>

<script>
import { reactive, toRef } from 'vue'
export default {
  setup () {
    const state = reactive({count: 1, name: 'diqiu'})
    const countRef = toRef(state, 'count')

    // console.log(countRef)
    // countRef.value ++
    // console.log(countRef, state.count)
    const count = state.count
    state.count = 10000

    console.log(state) // Proxy {count: "10000", name: "diqiu"}
    console.log(count) // 1
    console.log(countRef.value) // 10000

    // console.log(countRef, state.count)
    
    return {}
  }
}
</script>
