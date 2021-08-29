<template>
  <div>
    <p>reactive ref count: {{state.count}}</p>
    <p>ref count: {{count}}</p>
    <p ref="text">Hello</p>
  </div>
</template>

<script>
import { ref, reactive } from '@vue/composition-api'

export default {
  setup() {
    const count = ref(0)
    console.log('count.value: ', count.value)

    const state = reactive({ count })
    count.value++
    console.log('count.value: ', count.value)

    const text = ref(null)
    setTimeout(() => {
      console.log('text: ', text.value.innerHTML)
    }, 1000)

    return {
      state,
      count,
      text,
    }
  },
}
</script>
