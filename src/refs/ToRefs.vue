<template>
  <div>
    {{age}}
    {{name}}
  </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
  setup () {
    
    const state = reactive({
      age: 18,
      name: 'diqiu'
    })

    const stateAsRefs = toRefs(state)

    state.age ++
    console.log(stateAsRefs)
    console.log(state) // 
    return { ...stateAsRefs }
  }
}
</script>
