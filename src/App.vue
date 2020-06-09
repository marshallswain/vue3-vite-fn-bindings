<template>
  <div>
    <button @click="e => test()">Test</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const otherProp = ref(null)
    function test() {
      console.log(Object.keys(this))
    }
    return {
      otherProp,
      test
    }
  }
}
</script>
