<template>
  <q-modal position="top" ref="myCartModal" :content-css="{minWidth: '80vw', minHeight: '80vh'}">
    <q-modal-layout>
      <q-toolbar slot="header">
        <q-btn flat @click="$refs.myCartModal.close()">
          <q-icon name="keyboard_arrow_left" />
        </q-btn>
        <q-toolbar-title>
          カートの確認
        </q-toolbar-title>
        <q-btn flat @click="$refs.myCartModal.close()"><q-icon name="shopping_cart" /></q-btn>
      </q-toolbar>

      <q-toolbar slot="header">
        <q-btn @click="$refs.myCartModal.close()" class="bg-white text-primary full-width"><q-icon name="close" /> 閉じる</q-btn>
      </q-toolbar>

      <q-toolbar slot="footer" class="bg-black">
        <q-btn @click="$refs.myCartModal.close()" color="positive" class="full-width">購入確認画面へ進む<q-icon name="keyboard_arrow_right" /></q-btn>
      </q-toolbar>

      <div class="layout-padding">
        <h1>Modal</h1>

        <q-btn color="primary" @click="$refs.myCartModal.close()">Close</q-btn>
        <p class="caption" v-for="n in 15">This is a Modal presenting a Layout.</p>
      </div>
    </q-modal-layout>
  </q-modal>
</template>

<script>
  export default {
    methods: {
      openMyCart () {
        this.$refs.myCartModal.open()
      }
    },
    mounted () {
      let self = this
      this.$q.events.$on('openMyCart', () => {
        self.openMyCart()
      })
    },
    beforeDestroy () {
      this.$q.events.$off('openMyCart')
    }
  }
</script>

<style lang="stylus">
</style>
