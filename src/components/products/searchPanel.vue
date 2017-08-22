<template>
  <div>
    <q-toolbar color="white" class="justify-around search-panel">
      <q-btn outline color="primary" @click="openSortDialog" class="full-width">
        <q-icon name="swap_vert" />
        {{ sortSetting.text }}
      </q-btn>
      <q-btn outline color="primary" @click="openFilterModal" class="full-width">
        <q-icon name="filter_list" />
        絞り込み
      </q-btn>
    </q-toolbar>
    <filter-modal></filter-modal>
  </div>
</template>

<script>
  import { Dialog, Toast } from 'quasar'
  import FilterModal from './filterModal'
  export default {
    data () {
      return {
        sortSetting: {
          text: '並び替え',
          selected: 'latest',
          items: [
            {label: '新着順', value: 'latest', color: 'secondary'},
            {label: '人気順', value: 'popular'},
            {label: '五十音順', value: 'alphabet'}
          ]
        }
      }
    },
    components: {
      FilterModal
    },
    methods: {
      openSortDialog () {
        let self = this
        Dialog.create({
          title: '並び替え',
          message: '商品を表示する順番を指定してください。',
          form: {
            option: {
              type: 'radio',
              model: this.sortSetting.selected,
              items: this.sortSetting.items
            }
          },
          buttons: [
            'Cancel',
            {
              label: 'Ok',
              handler (data) {
                self.sortSetting.selected = data.option
                self.setFilterTextByValue(data.option)
                Toast.create.info('商品の並び順を変更しました')
              }
            }
          ]
        })
      },
      setFilterTextByValue (value) {
        let item = this.sortSetting.items.find((item) => {
          return item.value === value
        })
        this.sortSetting.text = item.label
      },
      openFilterModal () {
        this.$q.events.$emit('openFilterModal')
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .search-panel button.q-btn
    margin 8px 4px !important
</style>