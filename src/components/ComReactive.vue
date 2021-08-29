<template>
  <div>
    <p>count: {{state.count}}</p>
  </div>
</template>

<script>
// export default {
//   setup() {
//     const state = { count: 0 }
//     setTimeout(() => {
//       state.count++
//     })
//     return { state }
//   },
// }

import { reactive } from '@vue/composition-api'

export default {
  setup() {
    const state = reactive({ count: 0 })

    setTimeout(() => {
      state.count++
    }, 1000)

    return { state }
  },
}
</script>
