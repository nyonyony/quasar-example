<template>
  <div class="filter-list">
    <template v-for="(filter, index) in filters">
      <div class="item-wrap">
        <q-item @click="filter.open = !filter.open">
          <q-item-side v-if="countChecked(filters[index]) > 0" icon="done" color="positive" />
          <q-item-side v-else icon="crop_din" color="grey-6" />
          <q-item-main>
            <q-item-tile label>{{ filter.title }}
              <span v-if="countChecked(filters[index]) > 0">{{ countChecked(filters[index]) }} selected</span>
            </q-item-tile>
          </q-item-main>
          <q-item-side right>
            <q-item-tile v-if="filter.open" icon="remove" color="red" />
            <q-item-tile v-else="filter.open" icon="add" color="red" />
          </q-item-side>
        </q-item>
        <q-slide-transition>
          <div v-if="filter.open">
            <q-list link class="no-border">
              <q-item tag="label" v-for="selection in filter.selection" :key="selection.id">
                <q-item-main>
                  <q-item-tile title>{{ selection.label }}</q-item-tile>
                </q-item-main>
                <q-item-side right>
                  <q-checkbox v-model="selection.checked" />
                </q-item-side>
              </q-item>
            </q-list>
          </div>
        </q-slide-transition>
        <q-toolbar color="white" v-if="countChecked(filters[index])">
          <search-label v-for="selection in filter.selection"
                        v-if="selection.checked"
                        :key="selection.id"
                        :label="selection.label"
                        :color="selection.color">
          </search-label>
        </q-toolbar>
      </div>
      <q-item-separator></q-item-separator>
    </template>
  </div>
</template>

<script>
  import SearchLabel from './searchLabel.vue'
  export default {
    components: { SearchLabel },
    data () {
      return {
        filters: [
          {
            title: 'category',
            open: false,
            selection: [
              { id: 1, label: 'Food', color: 'primary', checked: false },
              { id: 2, label: 'Toy', color: 'secondary', checked: false }
            ]
          },
          {
            title: 'food form',
            open: false,
            selection: [
              { id: 1, label: 'Food', color: 'primary', checked: false },
              { id: 2, label: 'Toy', color: 'secondary', checked: false }
            ]
          }
        ]
      }
    },
    methods: {
      countChecked (filter) {
        let count = 0
        for (let item of filter.selection) {
          if (item.checked) count++
        }
        return count
      }
    }
  }
</script>

<style lang="stylus">
  .filter-list
    margin-top 16px
</style>
