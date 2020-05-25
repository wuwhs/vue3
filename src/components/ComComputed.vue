<template>
  <div>
    <p>count: {{count}}</p>
    <p>plusOne: {{plusOne}}</p>
  </div>
</template>

<script>
import { ref, computed } from '@vue/composition-api'

export default {
  setup() {
    const count = ref(0)
    // const plusOne = computed(() => count.value + 1)
    const plusOne = computed({
      get: () => count.value + 1,
      set: val => {
        count.value = val - 1
      }
    })
    plusOne.value = 10
    console.log('plusOne.value: ', plusOne.value)
    console.log('count.value: ', count.value)
    return {
      count,
      plusOne
    }
  }
}
</script>
