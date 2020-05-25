<template>
  <div>
    <h3>parent</h3>
    <p>treasure：{{treasure}}</p>
    <hr>
    <com-child />
  </div>
</template>

<script>
import { inject } from '@vue/composition-api'
import ComChild from './ComChild.vue'

export default {
  components: {
    ComChild
  },
  setup() {
    const treasure = inject('treasure')
    return {
      treasure
    }
  }
}
</script>
