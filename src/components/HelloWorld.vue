<template>
  <div>
    <button>Test</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    model: Object
  },
  setup(props, context) {
    const Test = props.model
    console.log(Test)
    return {}
  }
}
</script>
