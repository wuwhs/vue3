<template>
  <!-- <div>
    <h4>parent</h4>
    <p>treasure：{{treasure}}</p>
  </div> -->
  <!-- <button>
    <slot>Submit</slot>
  </button> -->
  <div class="container">
    <header>
      <slot name="header"
        :user="user" />
    </header>
    <main>
      <slot name="main" />
    </main>
    <footer>
      <slot name="footer" />
    </footer>

  </div>
</template>

<script>
// import { inject } from '@vue/composition-api'

export default {
  // setup() {
  //   const treasure = inject('treasure')
  //   return {
  //     treasure
  //   }
  // }
  data() {
    return {
      user: {
        name: 'win',
      },
    }
  },
}
</script>
