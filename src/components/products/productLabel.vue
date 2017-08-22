<template>
  <base-label :label="label" :color="color" :small="true" :tagged="true" :square="true"></base-label>
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

<style lang="stylus">
  .docs-chip .q-chip
    margin 5px
</style>
