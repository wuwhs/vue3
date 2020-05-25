<template>

  <div>
    <p>count: {{count}}</p>
    <button @click="increment">+1</button>
  </div>

  <!--
  <div>
    <p>count: {{state.count}}</p>
    <button @click="increment">+1</button>
  </div>
   -->
  <!--
  <div></div>
   -->
  <!-- <div>
    <input type="text"
      v-model="keyword">
  </div> -->
</template>

<script>
import { ref, watch } from '@vue/composition-api'

export default {
  setup() {
    // 监视 ref 数据源
    const count = ref(0)
    const stop = watch(count, (newVal, oldVal) => {
      console.log('newVal: ', newVal)
      console.log('oldVal: ', oldVal)
    })
    setTimeout(() => {
      stop()
    }, 3000)
    const increment = () => {
      count.value++
    }
    return {
      count,
      increment
    }
  }
}

// ---------------------------

// import { reactive, watch } from '@vue/composition-api'

// export default {
//   setup() {
//     // 监视 reactive 数据源
//     const state = reactive({
//       count: 0
//     })
//     const stop = watch(
//       () => state.count,
//       (newVal, oldVal) => {
//         console.log('newVal: ', newVal)
//         console.log('oldVal: ', oldVal)
//         setTimeout(() => {
//           stop()
//         }, 3000)
//       }
//     )
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

// import { watch, reactive } from '@vue/composition-api'
// export default {
//   setup() {
//     const state = reactive({ count: 0, name: 'zs' })
//     watch(
//       [() => state.count, () => state.name],
//       ([newCount, newName], [oldCount, oldName]) => {
//         console.log('newCount: ', newCount)
//         console.log('newName: ', newName)
//         console.log('............')
//         console.log('oldCount: ', oldCount)
//         console.log('oldName: ', oldName)
//       },
//       { lazy: true }
//     )

//     setTimeout(() => {
//       state.count = 1
//       state.name = 'ls'
//     }, 1000)
//   }
// }

// ---------------------------

// import { watch, ref } from '@vue/composition-api'
// export default {
//   setup() {
//     const count = ref(0)
//     const name = ref('zs')
//     watch(
//       [count, name],
//       ([newCount, newName], [oldCount, oldName]) => {
//         console.log('newCount: ', newCount)
//         console.log('newName: ', newName)
//         console.log('............')
//         console.log('oldCount: ', oldCount)
//         console.log('oldName: ', oldName)
//       },
//       {
//         lazy: true
//       }
//     )

//     setTimeout(() => {
//       count.value = 1
//       name.value = 'ls'
//     }, 1000)
//   }
// }

// ---------------------------

// import { ref, watch } from '@vue/composition-api'
// export default {
//   setup() {
//     const keyword = ref('')
//     const asyncPrint = val => {
//       return setTimeout(() => {
//         console.log('user input: ', val)
//       })
//     }

//     watch(
//       keyword,
//       (newVal, oldVal, onCleanUp) => {
//         const timer = asyncPrint(keyword)
//         onCleanUp(() => clearTimeout(timer))
//       },
//       {
//         lazy: true
//       }
//     )
//     return {
//       keyword
//     }
//   }
// }
</script>
