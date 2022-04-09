<template>
  <div id="root">
    <Header :isDark="isDark" />
  </div>
</template>

<script>
import Header from '../components/Header'
export default {
  //how do I add a class when I hover?
  //how do I append child?
  //how do I link in-page?
  //how do I pass props to nested children?
  name: 'app',

  data() {
    return {
      root: null,
      isDark: null,
    }
  },

  watch: {
    
  },

  methods: {

  },

  mounted() {
    this.root = document.documentElement
    if ( this.root.classList.contains('dark') ) this.isDark === true
    else this.isDark === false
  }
}
</script>

<style>