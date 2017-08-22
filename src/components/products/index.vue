<template>
  <div class="layout-padding">
    <search-panel></search-panel>
    <q-card-separator />
    <div class="row">
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
      <product-item></product-item>
    </div>
  </div>
</template>

<script>
  import ProductItem from './productItem'
  import SearchPanel from './searchPanel'
  export default {
    components: {
      ProductItem,
      SearchPanel
    },
    data () {
      return {
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~variables'
  @media screen and (max-width: $breakpoint-sm)
    .layout-padding
      padding: 0
</style>
