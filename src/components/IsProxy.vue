<template>
  <div>
    <!-- readonly {{original.count}} {{copy.count}} -->
  </div>
</template>

<script>
import { ref, reactive, readonly, isProxy } from "vue";
export default {
  setup() {
    const reactiveObj = reactive({
      count: 0,
    })
    const refObj = ref(0)
    const readonlyObj = readonly(reactiveObj)
    const obj = { a: 0 }
    const handler = {
      get: function (obj, prop) {
        return prop in obj ? obj[prop] : 37
      }
    }
    const p = new Proxy({}, handler)

    console.log(isProxy(reactiveObj)) // true
    console.log(isProxy(refObj)) // false
    console.log(isProxy(readonlyObj)) // true
    console.log(isProxy(obj)) // false
    console.log(isProxy(p)) // true
  },
}
</script>

<style scoped>
</style