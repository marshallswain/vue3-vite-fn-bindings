<template>
  <div>
    <button @click="e => fn()">Fn</button>
    <button @click="e => nested.util()">Nested Fn</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const someRef = ref(null)

    // this === vm
    function fn() {
      console.log(Object.keys(this)) // --> ['someRef', 'fn', 'nested']
    }

    const nested = {
      util() {
        console.log(Object.keys(this)) // --> ['util', 'prop']
      },
      prop: true
    }

    return {
      someRef,
      fn,
      nested
    }
  }
}
</script>
