<template>
  <div>
    <q-toolbar slot="header" class="">
      <q-btn
        flat round
        @click="toggleSidebarEvent"
      >
        <q-icon name="menu" />
        menu
      </q-btn>
      <q-toolbar-title>
        NOLEM SHOP
        <div slot="subtitle">subtitle comes here</div>
      </q-toolbar-title>
      <q-tabs inverted align="justify" class="text-white">
        <q-tab  v-if="searchMode" @click="searchMode = false" slot="title" class="text-white" icon="close" />
        <q-tab  v-else @click="searchMode = true" slot="title" class="text-white" icon="search" />
        <q-tab @click="openMyCart" count="0" slot="title" class="text-white" icon="shopping_cart" />
      </q-tabs>
    </q-toolbar>
    <q-toolbar v-if="searchMode">
      <q-toolbar-title>
        <q-transition
          appear
          enter="fadeIn"
          leave="fadeOut"
        >
          <q-search icon="search"
                    color="bg-white primary-text"
                    inverted v-model="searchTerm"
                    placeholder="Search by name, brands, etc" />
        </q-transition>
      </q-toolbar-title>
    </q-toolbar>
    <my-cart></my-cart>
  </div>
</template>

<script>
  import MyCart from '../shared/myCart'
  export default {
    data () {
      return {
        searchTerm: '',
        searchMode: false
      }
    },
    components: { MyCart },
    mounted () {
      console.log(this.$q)
    },
    methods: {
      toggleSidebarEvent () {
        this.$q.events.$emit('toggleSidebar')
      },
      openMyCart () {
        this.$q.events.$emit('openMyCart')
      }
    }
  }
</script>
