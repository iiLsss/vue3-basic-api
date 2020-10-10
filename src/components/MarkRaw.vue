<template>
  <div>

  </div>
</template>

<script>
import { isReactive, markRaw, reactive } from 'vue'
export default {
  setup () {
    const obj = markRaw({count: 0})
    // 通过markRaw 对obj增加属性 __v_skip: true
    console.log(obj) // {count: 0, __v_skip: true}
    const state = reactive(obj)
    console.log(state) // {count: 0, __v_skip: true}
    console.log(isReactive(state)) // false

    return {}
  }
}
</script>
