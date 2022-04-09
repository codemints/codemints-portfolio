<template>
  <section id="intro" class="[ text-center ]">
    <h1 class="[ text-theme-600 dark:text-theme-100 ]">{{ introText }}</h1>
    <h2 class="[ font-body ] [ text-theme-400 dark:text-theme-100 ]"> And I'm A <span class="[ block__hover ]">Creative</span> Frontend <span class="[ block__hover ]">Developer</span> With Roots In <span class="[ block__hover ]">Design</span></h2>
    <NuxtLink to="/contact" class="[ button ] [ mx-auto mt-16 ]">let's work together</NuxtLink>
    <a href="" class="function__link">(section) => { return this.next(section) }</a>
  </section>
</template>

<script>
export default {
  name: 'IntroSection',

  data() {
    return {
      introText: 'Hello. My Name Is LT.',
      splitText: '',
    }
  },

  methods: {
    
  }
}
</script>

<style scoped>
  #intro {
    position: relative;
    /* border: 2px solid red; */
  }
  h1, h2 {
    cursor: pointer;
  }
  h1 {
    font-size: 9.6rem;
    font-weight: 700;
  }

  h2 {
    font-size: 2.8rem;
    font-weight: 400;
    margin-top: 1rem;
  }

  

</style>