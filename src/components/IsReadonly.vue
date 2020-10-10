<template>
  <div>

  </div>
</template>

<script>
import { isReactive, isReadonly, reactive, readonly } from 'vue'
export default {
  setup () {
    const state = reactive({count: 0})
    const copy = readonly(state)
    const obj = { a: 0 }
    const handler = {
      get: function (obj, prop) {
        return prop in obj ? obj[prop] : 37
      }
    }
    const p = new Proxy({}, handler)
    console.log(isReadonly(state)) // false
    console.log(isReadonly(copy)) // true
    console.log(isReadonly(p)) // true
    return {}
  }
}
</script>
