<template>
  <div></div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'
export default {
  beforeCreate() {
    console.log('beforeCreate')
  },
  setup(props, context) {
    console.log('this: ', this)
    console.log('setup')
    console.log('props: ', props)
    console.log('context: ', context)
  },
  created() {
    console.log('created')
  }
}
</script>
