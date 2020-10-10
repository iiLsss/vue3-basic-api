<template>
  <div>
    <!-- readonly {{original.count}} {{copy.count}} -->
  </div>
</template>

<script>
import { reactive, readonly, watchEffect, isProxy } from 'vue'
export default {
  setup() {
    // const original = reactive({
    //   count: 100
    // })
    // const copy = readonly(original)
    // setTimeout(() =>{
    //   original.count = 10000
    // }, 1000)
    // console.log(copy)
    // // copy.count = 10000 // Set operation on key "count" failed: target is readonly.


    // return {
    //   original,
    //   copy
    // }

    const original = reactive({ count: 0 })
    const copy = readonly(original)
    const abc = {a: 1}
    watchEffect(() => {
      // 依赖追踪
      console.log(copy.count)
    });
    // original 上的修改会触发 copy 上的侦听
    original.count++;
    // 无法修改 copy 并会被警告
    copy.count++; // warning!

    console.log(isProxy(original))
    console.log(isProxy(copy))
    console.log(isProxy(abc))
    console.log(isProxy())
  }
}
</script>

<style scoped>

</style>