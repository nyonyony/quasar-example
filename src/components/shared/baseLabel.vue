<template>
  <q-chip :small="small" :tag="tagged" :square="square" :color="color">{{ label }}</q-chip>
</template>

<script>
  export default {
    props: {
      label: {
        type: String,
        required: true
      },
      color: {
        type: String,
        required: true
      },
      small: {
        type: Boolean,
        default: false
      },
      tagged: {
        type: Boolean,
        default: false
      },
      square: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style lang="stylus">
  .docs-chip .q-chip
    margin 5px
</style>
