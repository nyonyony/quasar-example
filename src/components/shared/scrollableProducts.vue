<template>
  <div class="layout-padding bg-light scrollable-section">
    <div class="row justify-between items-center">
      <div class="col scrollable-title">
        <h6 class="scrollable-title">Shop by Brands</h6>
      </div>
      <div class="col text-right">
        <a>Shop All
          <q-icon class="red-text" name="keyboard_arrow_right" />
        </a>
      </div>
    </div>
    <div class="scrollable-wrapper">
      <div class="q-carousel-left-button row flex-center scrollable-btn">
        <q-icon name="keyboard_arrow_left" />
      </div>
      <div class="row no-wrap scrollable-area" ref="scrollable">
        <div class="col-xs-5 col-sm-4 col-md-3">
          <router-link to="/products">
            <q-card class="scrollable-item bg-white">
              <q-card-media class="media-container">
                <img src="https://www.chewy.com/assets/img/_mobile/home/autoship/natures-variety.20170510.jpg">
              </q-card-media>
              <q-card-title slot="overlay" class="text-center scrollable-item-title">
                <a>Hill's</a>
              </q-card-title>
            </q-card>
          </router-link>
        </div>
        <div class="col-xs-5 col-sm-4 col-md-3">
          <router-link to="/products">
            <q-card class="scrollable-item bg-white">
              <q-card-media class="media-container">
                <img src="https://www.chewy.com/assets/img/_mobile/home/autoship/natures-variety.20170510.jpg">
              </q-card-media>
              <q-card-title slot="overlay" class="text-center scrollable-item-title">
                <a>Hill's</a>
              </q-card-title>
            </q-card>
          </router-link>
        </div>
        <div class="col-xs-5 col-sm-4 col-md-3">
          <router-link to="/products">
            <q-card class="scrollable-item bg-white">
              <q-card-media class="media-container">
                <img src="https://www.chewy.com/assets/img/_mobile/home/autoship/natures-variety.20170510.jpg">
              </q-card-media>
              <q-card-title slot="overlay" class="text-center scrollable-item-title">
                <a>Hill's</a>
              </q-card-title>
            </q-card>
          </router-link>
        </div>
        <div class="col-xs-5 col-sm-4 col-md-3">
          <router-link to="/products">
            <q-card class="scrollable-item bg-white">
              <q-card-media class="media-container">
                <img src="https://www.chewy.com/assets/img/_mobile/home/autoship/natures-variety.20170510.jpg">
              </q-card-media>
              <q-card-title slot="overlay" class="text-center scrollable-item-title">
                <a>Hill's</a>
              </q-card-title>
            </q-card>
          </router-link>
        </div>
        <div class="col-xs-5 col-sm-4 col-md-3">
          <router-link to="/products">
            <q-card class="scrollable-item bg-white">
              <q-card-media class="media-container">
                <img src="https://www.chewy.com/assets/img/_mobile/home/autoship/natures-variety.20170510.jpg">
              </q-card-media>
              <q-card-title slot="overlay" class="text-center scrollable-item-title">
                <a>Hill's</a>
              </q-card-title>
            </q-card>
          </router-link>
        </div>
      </div>
      <div class="q-carousel-right-button row flex-center scrollable-btn">
        <q-icon class="red-text" name="keyboard_arrow_right" />
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        products: [
          {
            title: 'Hill¥`s',
            imageUrl: 'https://www.chewy.com/assets/img/_mobile/home/autoship/hills-prescription.20170221.jpg'
          },
          {
            title: 'Hill¥`s',
            imageUrl: 'https://www.chewy.com/assets/img/_mobile/home/autoship/hills-prescription.20170221.jpg'
          }
        ]
      }
    },
    mounted () {
      let area = this.$refs.scrollable
      console.log(area)
    }
  }
</script>

<style lang="stylus" scoped>
  .scrollable-section
    padding-top 8px
  .scrollable-title
    padding 4px
  .scrollable-btn
    z-index 2
  .scrollable-wrapper
    position relative
  .scrollable-area
    width 100%
    overflow scroll
  .scrollable-item
    margin-left 4px
    margin-right 4px
    .scrollable-item-title
      padding 8px 4px
  .media-container
    padding 8px
</style>
