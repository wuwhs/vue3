<template>
  <div>
    <p>count: {{count}}</p>
    <button @click="increment">+1</button>
  </div>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api'

export default {
  setup() {
    const state = reactive({
      count: 0
    })

    const increment = () => {
      state.count++
    }

    return {
      ...toRefs(state),
      increment
    }
  }
}
</script>
