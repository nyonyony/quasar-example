<template>
  <q-modal ref="filterModal" maximized :content-css="{minWidth: '80vw', minHeight: '80vh'}">
    <q-modal-layout>
      <q-toolbar slot="header">
        <q-btn flat @click="$refs.filterModal.close()">
          <q-icon name="keyboard_arrow_left" />
        </q-btn>
        <q-toolbar-title>
          絞り込み
        </q-toolbar-title>
        <q-btn flat @click="$refs.filterModal.close()">
          close
          <q-icon name="close" />
        </q-btn>
      </q-toolbar>

      <q-toolbar slot="footer" class="bg-black">
        <q-btn @click="$refs.filterModal.close()" color="faded" class="full-width">キャンセル</q-btn>
        <q-btn @click="$refs.filterModal.close()" color="positive" class="full-width">確定</q-btn>
      </q-toolbar>
      <filter-list></filter-list>
    </q-modal-layout>
  </q-modal>
</template>

<script>
  import FilterList from './filterList.vue'
  export default {
    components: { FilterList },
    data () {
      return {
        list: false,
        multipleSelect: ['goog', 'twtr'],
        options: [
          {
            label: 'Google',
            value: 'goog'
          },
          {
            label: 'Facebook',
            value: 'fb'
          },
          {
            label: 'Twitter',
            value: 'twtr'
          },
          {
            label: 'Apple Inc.',
            value: 'appl'
          },
          {
            label: 'Oracle',
            value: 'ora'
          }
        ]
      }
    },
    methods: {
      openFilterModal () {
        this.$refs.filterModal.open()
      },
      countChecked (filter) {
        let count = 0
        for (let item of filter.selection) {
          if (item.checked) count++
        }
        return count
      }
    },
    mounted () {
      let self = this
      this.$q.events.$on('openFilterModal', () => {
        self.openFilterModal()
      })
    },
    beforeDestroy () {
      this.$q.events.$off('openFilterModal')
    }
  }
</script>

<style lang="stylus">
</style>
