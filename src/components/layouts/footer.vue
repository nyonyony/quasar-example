<template>
  <div>
    <q-toolbar slot="header" inverted class="row">
      <q-btn flat class="col text-faded">
        <div class="column">
          <q-icon name="shopping_cart" />
          test
        </div>
      </q-btn>
      <q-btn flat class="col text-faded"><q-icon name="shopping_cart" />tst</q-btn>
      <q-btn flat class="col text-faded"><q-icon name="shopping_cart" />sss</q-btn>
    </q-toolbar>
    <q-list>
      <q-list-header inset>Links</q-list-header>
      <q-item>
        <q-item-main>
          <q-item-tile sublabel>Privacy Policy</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-item>
        <q-item-main>
          <q-item-tile sublabel>Terms of Condition</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-item>
        <q-item-main>
          <q-item-tile sublabel>Trade</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-item>
        <q-item-main>
          <q-item-tile sublabel>About Us</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-item>
        <q-item-main>
          <q-item-tile sublabel>Our Story</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-list-header inset>Support</q-list-header>
      <q-item>
        <q-item-side icon="phone" inverted color="grey-6" />
        <q-item-main>
          <q-item-tile label>080-5523-0922</q-item-tile>
          <q-item-tile sublabel>046-111-1111</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
      <q-item-separator />
      <q-item>
        <q-item-side icon="email" inverted color="grey-6" />
        <q-item-main>
          <q-item-tile label>kazuya311@gmail.com</q-item-tile>
        </q-item-main>
        <q-item-side right icon="keyboard_arrow_right" />
      </q-item>
    </q-list>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        searchTerm: '',
        searchMode: false
      }
    },
    mounted () {
      console.log(this.$q)
    },
    methods: {
      toggleSidebarEvent () {
        this.$q.events.$emit('toggleSidebar')
      }
    }
  }
</script>
