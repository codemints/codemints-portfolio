<template>
  <header class="[ bg-theme-200 dark:bg-theme-700 ]">
    <section>
      <Social />
      <img :src="switchLogo" alt="site logo">
      <Toggle />
    </section>
    <NavMain />
    <ScrollSpy />
  </header>
  
</template>

<script>
import Toggle from './Toggle'
import Social from './Social'
import NavMain from './NavMain'
import ScrollSpy from 'comp/ScrollSpy'
import logoLight from 'img/logo-light.png'
import logoDark from 'img/logo-dark.png'

export default {
  name: 'Header',

  props: [
    'isDark'
  ],

  data() {
    return {
      logoLight,
      logoDark, 
    }
  },

  methods: {
    },

  mounted() {
    
    },

  computed: {
    switchLogo() {
      return this.isDark ? this.logoDark : this.logoLight;
    }
  },
}
</script>

<style scoped>

  section {
    display: flex;
    align-items: center;
    position: relative;
    width: 100vw;
    padding-inline: 5rem;
    padding-block: 2rem;
  }

  section > * {
    flex: 1 0 33%;
  }

  img {
    max-width: 8.5rem;
    width: 100%;
    transition: var(--base);
  }

  img:hover {
    filter:grayscale(1);
  }

</style>
