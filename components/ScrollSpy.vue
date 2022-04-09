<template>
  <div class="[ scrollspy ] [ bg-theme-200 dark:bg-theme-700 ]">
    <div class="[ scroll__position ] [ bg-theme-orange ]"></div>
  </div>
</template>

<script>
export default {
  name: 'ScrollSpy'
}
</script>

<style scoped>
  .scroll__position {
    height: 2rem;
    width: 10vw;
  }
</style>