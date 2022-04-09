<template>
  <div class="[ theme__switcher ]">

    <p class="[ switcher__text ] [ text-theme-300 dark:text-theme-100 ]">site(dark)</p>

    <div class="[ bg-theme-600 dark:bg-theme-800 ] [ toggle__bg" ]>

      <div>
        <label for="toggle__dark">dark theme toggle</label>

        <input
          type="radio"
          id="toggle__dark"
          :value="true"
          v-model="dark"
          class="[ theme__toggle--button ]"
          >
      </div>

      <div>
        <label for="toggle__light">light theme toggle</label>

        <input
          type="radio"
          id="toggle__light" 
          :value="false"
          v-model="dark"
          class="[ theme__toggle--button ]"
          >
      </div>
      
      <div class="[ switch__wrapper ]" :class="togglePosition">
        <div class="[ toggle__switch ] [ bg-theme-blue ]"></div>
      </div>

    </div>

    <p class="[ switcher__text ] [ text-theme-600 dark:text-theme-500 ]">site(light)</p>
  </div>
</template>

<script>
export default {
  name: 'Toggle',

  props: [
    'isDark',
    'updateMode',
  ],
  
  data() {
    return {
      dark: this.isDark,
      watchDark: false,
    }
  },
  
  computed: {
    //sets the postiion of the toggle based on initial isDark value
    togglePosition() {
      return {
        'position__dark': this.dark,
        'position__light': !this.dark
      }
    }
  },

  watch: {
    //updates root isDark data value based on user input from radio buttons
    dark() {
      this.updateMode(this.dark)
    },
  },

  created() {
    //watches for initial change in isDark prop from root component
    //if change updates this data clone to match
    //self closes after update
    this.unwatchDark = this.$watch('isDark', (newValue) => {
      if ( newValue ) {
        this.dark = newValue
        this.unwatchDark();
      }
    })
  }
}
</script>

<style scoped>
  .theme__switcher {
    --toggle-padding: 0.6rem;
    --toggle-dimension: 1.75rem;
    --toggle-radius: calc( var(--toggle-dimension) / 2 );
    
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1.5rem;
  }
  .toggle__bg {
    position: relative;
    min-width: min(6rem, 10rem);
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
    border: none;
  }

  input:hover {
    opacity: 0.2;
  }
  
  .switch__wrapper {
    width: 100%;
    pointer-events: none;
    transition: var(--bounce);
  }
  
  .position__dark {
    transform: translateX( 0 );
  }

  .position__light {
    transform: translateX(calc( 100% - var(--toggle-dimension) ));
  }
  
  .toggle__switch {
    position: relative;
    height: var(--toggle-dimension);
    width: var(--toggle-dimension);
    border-radius: var(--toggle-radius);
    cursor: pointer;
    pointer-events: none;
    z-index: 1;
  }
  
</style>