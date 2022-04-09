<template>
  <header class="[ bg-theme-200 dark:bg-theme-700 ]">
    <section>
      <Social class="[ social__wrapper ]"/>
      <div class="[ logo__wrapper ]"><img :src="switchLogo" alt="site logo"></div>
      <Toggle class="[ toggle__wrapper ]" :isDark="isDark" :updateMode="updateMode"/>
    </section>
    <NavMain/>
    <ScrollSpy />
  </header>
  
</template>

<script>
import Toggle from './Toggle'
import Social from './Social'
import NavMain from './NavMain'
import ScrollSpy from './ScrollSpy'
import logoLight from 'img/logo-light.png'
import logoDark from 'img/logo-dark.png'

export default {
  name: 'Header',

  props: [
    'isDark',
    'updateMode',
  ],

  data() {
    return {
      logoLight,
      logoDark,
    }
  },

  computed: {
    //watches for change in isDark data from parent component
    //changes src of logo image based on value
    switchLogo() {
      return this.isDark ? this.logoDark : this.logoLight;
    }
  },
}
</script>

<style scoped>

  section {
    display: grid;
    grid-template-columns: repeat( auto-fit, minmax(32rem, 1fr));
    grid-gap: 1.5rem;
    align-content: center;
    position: relative;
    width: 100vw;
    padding-inline: 1rem;
    padding-block: 3rem;
  }

  .logo__wrapper {
    grid-area: 1/1/2/2
  }

  img {
    max-width: 8.5rem;
    width: 100%;
    margin-inline: auto;
    transition: var(--base);
  }

  img:hover {
    filter:grayscale(1);
  }

  @media only screen and (min-width: 76.8rem) {
    section {
      padding-inline: 5rem;
      padding-block: 2rem;
    }
    .logo__wrapper {
      grid-area: unset;
    }
  }

</style>
