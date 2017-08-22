<template>
  <!-- Don't drop "q-app" class -->
  <div id="q-app">
    <!-- Determine if front or admin -->
    <router-view />
  </div>
</template>

<script>
/*
 * Root component
 */
export default {}
</script>

<style lang="stylus">
  .no-margin
    margin 0
  .no-padding
    padding: 0
  .bg-white
    background-color: white
  .bg-light
    background-color $light
</style>
