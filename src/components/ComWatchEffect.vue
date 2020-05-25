<template>

  <!-- <div>
    <p>count: {{count}}</p>
    <button @click="increment">+1</button>
  </div> -->

  <!-- <div>
    <p>count: {{state.count}}</p>
    <button @click="increment">+1</button>
  </div> -->

  <!-- <div></div> -->

  <div>
    <input type="text"
      v-model="keyword">
  </div>

</template>

<script>
// import { ref, watchEffect } from '@vue/composition-api'

// export default {
//   setup() {
//     // 监视 ref 数据源
//     const count = ref(0)
//     // 监视依赖有变化，立刻执行
//     watchEffect(() => {
//       console.log('count.value: ', count.value)
//     })
//     const increment = () => {
//       count.value++
//     }
//     return {
//       count,
//       increment
//     }
//   }
// }

// ---------------------------

// import { reactive, watchEffect } from '@vue/composition-api'

// export default {
//   setup() {
//     // 监视 reactive 数据源
//     const state = reactive({
//       count: 0
//     })
//     const stop = watchEffect(() => {
//       console.log('state.count: ', state.count)
//     })
//     setTimeout(() => {
//       stop()
//     }, 3000)
//     const increment = () => {
//       state.count++
//     }
//     return {
//       state,
//       increment
//     }
//   }
// }

// ---------------------------

import { ref, watchEffect } from '@vue/composition-api'
export default {
  setup() {
    const keyword = ref('')
    const asyncPrint = val => {
      return setTimeout(() => {
        console.log('user input: ', val)
      }, 1000)
    }

    watchEffect(
      onInvalidate => {
        const timer = asyncPrint(keyword.value)
        onInvalidate(() => clearTimeout(timer))
        console.log('keyword change: ', keyword.value)
      },
      {
        flush: 'post', // 默认'post'，同步'sync'，'pre'组件更新之前
        // 追踪 reactive 和 ref 时触发
        onTrack(e) {
          console.log('track: ', e)
        },
        // 依赖变化时触发
        onTrigger(e) {
          console.log('trigger: ', e)
        }
      }
    )

    return {
      keyword
    }
  }
}
</script>
