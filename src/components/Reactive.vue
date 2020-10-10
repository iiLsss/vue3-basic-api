<template>
<div>
  <p><button @click="change(true)">支持</button> 支持：{{state.support}}</p>
  <p><button @click="change(false)">反对</button> 反对：{{state.oppose}}</p>
  <!-- <p>支持率：{{ratio}}}</p> -->

</div>
</template>

<script>
import { reactive } from 'vue'
export default {
  setup(props) {
    const state = reactive({
      support: 0,
      oppose: 0,
    })
    console.log(state)
    const change = (is) => {
      is ? state.support++ : state.oppose++
    }
    return {
      state,
      change
    }
  }
}
</script>