<template>
  <header>
    <Social />
    <img :src="logoLight" alt="site logo">
    <Toggle />
  </header>
  
</template>

<script>
import Toggle from './Toggle'
import Social from './Social'

export default {
  name: 'Header',

  props: [
    'isDark'
  ],

  data() {
    return {
      logoLight: './assets/img/logo-light.png',
      logoDark: './assets/img/logo-dark.png', 
    }
  },

  methods: {

  },

  mounted() {

  }
}
</script>

<style scoped>

</style>
