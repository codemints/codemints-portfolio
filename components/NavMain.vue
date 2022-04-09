<template>
  <nav class="[ nav__main ] [ bg-theme-600 dark:bg-theme-500 ]">
    <NuxtLink to="/" :class="classNames">site(intro)</NuxtLink>
    <NuxtLink to="/about" :class="classNames">about(me)</NuxtLink>
    <NuxtLink to="/work" :class="classNames">my(work)</NuxtLink>
    <NuxtLink to="/skills" :class="classNames">dev(skills)</NuxtLink>
    <NuxtLink to="/contact" :class="classNames">contact(info)</NuxtLink>
    <div class="[ nav__shuttle ] [ bg-theme-200 dark:bg-theme-blue ]"></div>
  </nav>
</template>

<script>
export default {
  name: 'NavMain',

  data() {
    return {
      root: null,
      classNames: [ 'text-theme-300', 'hover:text-theme-200', 'active:text-theme-200', 'focus:text-theme-200', 'active:text-theme-200', 'dark:text-theme-100', 'dark:hover:text-theme-blue', 'dark:focus:text-theme-blue', 'dark:active:text-theme-blue' ]
    }
  },

  methods: {

  },

  mounted() {
    
  }
}
</script>

<style scoped>
  nav {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 2.5rem;
    min-height: 5rem;
  }

  a {
    transform: translateY(-0.2rem);
    transition: var(--base);
  }

  .nav__shuttle {
    position: absolute;
    bottom: 1rem;
    height: 0.2rem;
    width: 2rem;
  }
</style>