<template>
  <!-- <reactive-comp /> -->
  <!-- <readonly /> -->
  <!-- <is-proxy /> -->
  <!-- <is-reactive /> -->
  <is-readonly />
</template>

<script>
import ReactiveComp from './components/Reactive.vue'
import Readonly from './components/Readonly.vue'
import IsProxy from './components/IsProxy.vue'
import IsReactive from './components/IsReactive.vue'
import IsReadonly from './components/IsReadonly.vue'
export default {
  name: 'App',
  components: {
    ReactiveComp,
    Readonly,
    IsProxy,
    IsReactive,
    IsReadonly

  }
}
</script>
