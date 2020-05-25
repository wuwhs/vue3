<template>
  <div>count: {{count}}</div>
</template>

<script>
import { ref, onMounted, onUpdated, onUnmounted } from '@vue/composition-api'
export default {
  setup() {
    onMounted(() => {
      console.log('mounted!')
    })
    onUpdated(() => {
      console.log('updated!')
    })
    onUnmounted(() => {
      console.log('unmounted!')
    })

    const count = ref(0)

    setTimeout(() => {
      count.value = 1
    }, 1000)

    return {
      count
    }
  }
}
</script>
