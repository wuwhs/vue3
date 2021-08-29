<template>
  <div id="app">
    <!-- <base-layout>
      <template v-slot:header="slotProp">
        <h1>Header</h1>
        <sub>{{slotProp.user.name}}</sub>
      </template>
      <template v-slot:main>
        <h2>main</h2>
      </template>
      <template v-slot:footer>
        <h3>footer</h3>
      </template>
    </base-layout> -->

    <!-- <com-setup /> -->
    <!-- <com-reactive /> -->
    <!-- <com-ref /> -->
    <!-- <com-reactive-ref /> -->
    <!-- <com-to-ref /> -->
    <!-- <com-computed /> -->
    <!-- <com-watch-effect /> -->
    <com-watch />
    <!-- <com-life-cycle-hooks v-if="show" /> -->
    <!-- <com-grandprent /> -->
    <!-- <define-component /> -->
  </div>
</template>

<script>
// import BaseLayout from './components/ComChild'
// import ComSetup from './components/ComSetup.vue'
// import ComReactive from './components/ComReactive.vue'
// import ComRef from './components/ComRef.vue'
// import ComReactiveRef from './components/ComReactiveRef.vue'
// import ComToRef from './components/ComToRef.vue'
// import ComComputed from './components/ComComputed.vue'
// import ComWatchEffect from './components/ComWatchEffect.vue'
import ComWatch from './components/ComWatch.vue'
// import ComLifeCycleHooks from './components/ComLifeCycleHooks.vue'
// import ComGrandprent from './components/ComGrandparent.vue'
// import DefineComponent from './components/DefineComponent.vue'

export default {
  name: 'App',
  components: {
    // BaseLayout,
    // ComSetup,
    // ComReactive,
    // ComRef,
    // ComReactiveRef,
    // ComToRef,
    // ComComputed,
    // ComWatchEffect,
    ComWatch,
    // ComLifeCycleHooks
    // ComGrandprent
    // DefineComponent
  },

  data() {
    return {
      show: true,
    }
  },

  created() {
    setTimeout(() => {
      this.show = false
    }, 2000)
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
