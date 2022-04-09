<template>
  <div id="root" :class="modeClassName">
    <Header :isDark="isDark" :updateMode="updateMode" />
    <IntroSection />
  </div>
</template>

<script>
import Header from 'comp/Header'
import IntroSection from 'comp/sections/Intro'

export default {
  name: 'app',

  components: {
    IntroSection
  },

  data() {
    return {
      isDark: null,
      isMode: null,
    }
  },

  watch: {
  },

  computed: {
    //set top level class to 'light' or 'dark' to trigger theme color styles
    modeClassName() {
      return this.isDark ? 'dark' : 'light'
    },
  },

  methods: {
    //update isDark & isMode data in parent
    //passed down to header & toggle components
    updateMode(mode) {
      this.isDark = mode
      this.isMode = this.isDark ? 'dark' : 'light'
      localStorage.setItem('themeMode', this.isMode)
    },
    
    //returns user system color preference, i.e. light or dark
    prefersMode(mode) {
      return window.matchMedia(`(prefers-color-scheme: ${mode})`)
    },

    //sets initial state based on user system color preference
    //sets persistent data based on user choice
    //if user choice exists in localStorage will set based on that
    setPrefersMode() {
      const local = localStorage.getItem('themeMode')
      if ( this.prefersMode('dark').matches && !local ) {
        this.updateMode(true)
      } else if ( !this.prefersMode('dark') && !local ) {
        this.updateMode(false)
      } else {
        const mode = ( local === 'dark' ) ? true : false
        this.updateMode(mode);
      }
    }
  },

  mounted() {
    //set inital state color mode
    this.setPrefersMode()
  },
}
</script>

<style>