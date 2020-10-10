<template>
  <div>
    {{age}}
    {{other.name}}
  </div>
</template>

<script>
import { isReactive, shallowReactive, toRefs, watch, watchEffect } from 'vue'
export default {
  setup () {
    const state = shallowReactive({
      age: 18,
      other: {
        name: 'diqiu',
      }
    })
    watch(() => state.age, () => {
      console.log('age', state) // age Proxy {age: 20, other: {…}}
    })
    // 改变数据不会触发监听
    watch(() => state.other.name, () => {
      console.log('other', state.other)
    })
    setTimeout(() => {
      state.age = 20
    }, 1000)
    setTimeout(() => {
      state.other.name = '娃哈哈'
    }, 5000)
    console.log(isReactive(state)) // true
    console.log(isReactive(state.age)) // false
    console.log(isReactive(state.other.name)) // false
    return {
      ...toRefs(state)
    }
  }
}
</script>
