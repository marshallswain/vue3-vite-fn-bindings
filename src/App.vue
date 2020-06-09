<template>
  <div>
    <button @click="e => fn()">Fn</button>
    <button @click="e => nested.fn()">Nested Fn</button>
  </div>
</template>

<script>
import { ref } from 'vue'

function fn() {
  console.log(Object.keys(this))
}

export default {
  name: 'App',
  setup() {
    const someRef = ref(null)

    const nested = {
      fn() {
        console.log(Object.keys(this))
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
