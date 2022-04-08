<template>
  <div class="[ theme__switcher ]">
    <p class="[ switcher__text ] [ text-theme-300 dark:text-theme-100 ]">site(dark)</p>
    <div class="[ bg-theme-600 dark:bg-theme-700 ] [ toggle__bg" ]>
      <div>
        <label for="toggle__dark">dark theme toggle</label>
        <input type="radio" id="toggle__dark" class="[ theme__toggle--button ]">
      </div>
      <div>
        <label for="toggle__light">light theme toggle</label>
        <input type="radio" id="toggle__light" class="[ theme__toggle--button ]">
      </div>
      <div class="[ toggle__switch ] [ bg-theme-blue ]"></div>
    </div>
    <p class="[ switcher__text ] [ text-theme-600 dark:text-theme-500 ]">site(light)</p>
  </div>
</template>

<script>
export default {
  name: 'Toggle',
  
  data() {
    return {
    }
  },
  mounted() {
    
  },
  created() {
    
  },

}
</script>

<style scoped>
  .theme__switcher {
    --toggle-padding: 0.75rem;
    --toggle-dimension: 2.25rem;
    --toggle-radius: calc( var(--toggle-dimension) / 2 );
    
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1.5rem;

    max-width: 25rem;
  }
  .toggle__bg {
    position: relative;
    min-width: min(7.5rem, 15rem);
    border-radius: 5rem;
    padding: var(--toggle-padding);
  }
  .toggle__bg > div:not(:last-of-type) {
    position: absolute;
    top: calc();
  }
  .toggle__bg > div:first-of-type {
    left: calc( 0px + var(--toggle-padding) );
  }
  .toggle__bg > div:nth-of-type(2) {
    right: calc( 0px + var(--toggle-padding));
  }
  label {
    position: absolute;
    visibility: hidden;
    height: 0;
    opacity: 0;
    overflow: hidden;
    transition: var(--base);
  }
  input {
    background-color: white;
    height: var(--toggle-dimension);
    width: var(--toggle-dimension);
    border-radius: var(--toggle-radius);
    opacity: 0.1;
    transition: var(--base);
  }

  input:hover {
    opacity: 0.2;
  }

  .toggle__switch {
    position: relative;
    height: var(--toggle-dimension);
    width: var(--toggle-dimension);
    border-radius: var(--toggle-radius);
    cursor: pointer;
    z-index: 1;
  }
</style>