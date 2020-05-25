<template>
  <div>
    <h4>parent</h4>
    <p>treasure：{{treasure}}</p>
  </div>
</template>

<script>
import { inject } from '@vue/composition-api'

export default {
  setup() {
    const treasure = inject('treasure')
    return {
      treasure
    }
  }
}
</script>
