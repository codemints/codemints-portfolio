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
  //how do I :class={ data.hoverClass: data.isHovered}
  //how do I link in-page?
  //how do I listen for events?
  //can I target the <template>?
  name: 'app',

  data() {
    return {
      root: null,
      isDark: false,
    }
  },

  methods: {
  },

  mounted() {
    this.root = document.documentElement;
    // this.root.classList.add('dark');
  }
}
</script>

<style>