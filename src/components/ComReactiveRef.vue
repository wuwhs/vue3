<template>
  <div>count: {{state.count1}}
  </div>
</template>

<script>
import { reactive, ref } from '@vue/composition-api'

export default {
  setup() {
    // const count = ref(0)
    // const state = reactive({ count })
    // console.log(state.count)
    // state.count++
    // console.log(state.count)
    // console.log(count.value)
    const count1 = ref(0)
    const state = reactive({ count1 })
    const count2 = ref(9)
    state.count1 = count2
    console.log(state.count1)
    console.log(count1.value)
    console.log(count2.value)
    return { state }
  },
}
</script>
