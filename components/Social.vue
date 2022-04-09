<template>
  <div class="[ fa-brands__wrapper ]">
    <a href="https://www.linkedin/codemints" target="_blank"><i class="fa-brands fa-linkedin-in"></i></a>
    <a href="https://www.codepen.io/codemints" target="_blank"><i class="fa-brands fa-codepen"></i></a>
    <a href="https://www.github.com/codemints" target="_blank"><i class="fa-brands fa-github-alt"></i></a>
  </div>
</template>

<script>
export default {
  name: 'Social'
}
</script>

<style>
  .fa-brands__wrapper {
    display: flex;
    align-items: center;
    gap: 1.5rem;
  }
  i.fa-brands {
    font-size: 3.2rem;
    color: var(--theme-300);
    transition: var(--base);
  }
  .dark i.fa-brands {
    color: var(--theme-500);
  }
  
  i.fa-brands:hover {
    color: var(--theme-blue);
  }
</style>