<template>
  <div>
    <h2>grandparent</h2>
    <p>treasure：{{treasure}}</p>
    <hr>
    <com-parent />
  </div>
</template>

<script>
import { ref, provide } from '@vue/composition-api'
import ComParent from './ComParent.vue'

export default {
  components: {
    ComParent
  },
  setup() {
    // let treasure = ['传国玉玺']

    // provide('treasure', treasure)

    // setTimeout(() => {
    //  treasure[0] = '尚方宝剑'
    // }, 1000)

    let treasure = ref('传国玉玺')

    provide('treasure', treasure)

    setTimeout(() => {
      treasure.value = '尚方宝剑'
    }, 1000)

    return {
      treasure
    }
  }
}
</script>
