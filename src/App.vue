<template>
  <!-- <reactive-comp /> -->
  <!-- <readonly /> -->
  <!-- <is-proxy /> -->
  <!-- <is-reactive /> -->
  <!-- <is-readonly /> -->
  <!-- <to-raw /> -->
  <!-- <mark-raw /> -->
  <!-- <shallow-reactive /> -->
  <!-- <shallow-readonly /> -->

  <ref-comp />
</template>

<script>
// import ReactiveComp from './components/Reactive.vue'
// import Readonly from './components/Readonly.vue'
// import IsProxy from './components/IsProxy.vue'
// import IsReactive from './components/IsReactive.vue'
// import IsReadonly from './components/IsReadonly.vue'
// import ToRaw from './components/ToRaw.vue'
// import MarkRaw from './components/MarkRaw.vue'
// import ShallowReactive from './components/ShallowReactive.vue'
// import ShallowReadonly from './components/ShallowReadonly.vue'

import RefComp from './refs/Ref.vue'

export default {
  name: 'App',
  components: {
    RefComp,
    // ReactiveComp,
    // Readonly,
    // IsProxy,
    // IsReactive,
    // IsReadonly,
    // ToRaw,
    // MarkRaw,
    // ShallowReactive,
    // ShallowReadonly
  }
}
</script>
