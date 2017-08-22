<template>
  <q-layout
    ref="layout"
    view="lHh Lpr fff"
    :left-class="{'bg-grey-2': true}"
    class="baseLayout"
  >
    <q-modal ref="layoutModal" :content-css="{minWidth: '80vw', minHeight: '80vh'}">
      <q-modal-layout>
        <q-toolbar slot="header">
          <q-btn flat @click="$refs.layoutModal.close()">
            <q-icon name="keyboard_arrow_left" />
          </q-btn>
          <div class="q-toolbar-title">
            Header
          </div>
        </q-toolbar>
        <q-toolbar slot="footer">
          <div class="q-toolbar-title">
            Footer
          </div>
        </q-toolbar>
        <div class="layout-padding">
          <h1>Modal</h1>
          <q-btn color="primary" @click="$refs.layoutModal.close()">Close</q-btn>
          <p class="caption" v-for="n in 15">This is a Modal presenting a Layout.</p>
        </div>
      </q-modal-layout>
    </q-modal>

    <navbar></navbar>

    <div slot="left">
      <sidebar></sidebar>
    </div>

    <!--
      Replace following <div> with
      <router-view /> component
      if using subRoutes
    -->
    <q-transition
      appear
      enter="slideIn"
      leave="fadeOut"
    >
      <!-- Wrapping only one DOM element, defined by QBtn -->
      <router-view />
    </q-transition>

    <footer-bar></footer-bar>

  </q-layout>
</template>

<script>
  import Sidebar from './sidebar'
  import Navbar from './navbar'
  import FooterBar from './footer'
  import 'quasar-extras/animate'

  export default {
    components: {
      Sidebar,
      Navbar,
      FooterBar
    },
    data () {
      return {
      }
    },
    methods: {
      toggleSidebar () {
        this.$refs.layout.toggleLeft()
      }
    },
    mounted () {
      let self = this
      this.$q.events.$on('toggleSidebar', () => {
        self.toggleSidebar()
      })
    },
    beforeDestroy () {
      this.$q.events.$off('toggleSidebar')
    }
  }
</script>

<style lang="stylus">
  @import '~variables'
</style>
