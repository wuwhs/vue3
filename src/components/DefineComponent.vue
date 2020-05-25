
<template>
<div></div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

const myComponent = defineComponent({
  setup() {
    console.log('defineComponent 为了类型推导');
  },
  render(h) {
    return h('div', null, 'defineComponent 为了类型推导')
  }
})
export default myComponent
</script>
