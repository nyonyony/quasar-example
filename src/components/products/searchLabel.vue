<template>
  <base-label class="search-label" :label="label" :color="color" :small="true" :square="true"></base-label>
</template>

<script>
  import BaseLabel from '@/shared/baseLabel'
  export default {
    components: { BaseLabel },
    props: {
      label: {
        type: String,
        required: true
      },
      color: {
        type: String,
        required: true
      }
    }
  }
</script>

<style lang="stylus" scoped="">
  .search-label
    margin-right 4px
</style>
