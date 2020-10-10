<template>
  <div>

  </div>
</template>

<script>
import { shallowReadonly } from 'vue'
export default {
  setup () {
    const state = shallowReadonly({
      count: 1,
      other: {
        name: 'diqiu'
      }
    })

    state.count = 10 // vue.js:629 Set operation on key "count" failed: target is readonly
    state.other.name = 'iiLsss'
    console.log(state) // {count: 1, other: {name: 'iiLsss'}}

    return {}
  }
}
</script>
