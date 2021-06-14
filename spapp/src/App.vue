<template>
  <TheNavigation />
  <main class="content">
    <router-view />
  </main>
</template>

<script>
  import TheNavigation from '@/components/TheNavigation.vue';
  export default {
    components: {
      TheNavigation,
    },
    
  }
</script>

<style lang="scss">
  @import './assets/scss/main.scss';
</style>
