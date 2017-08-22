<template>
  <div class="product-item col-xs-12 col-sm-4 col-md-3">
    <q-card class="row sm-hide md-hide lg-hide xl-hide card-sp no-shadow">
      <div class="col-xs-4">
        <q-card-media class="col-xs-4 media-container">
          <category-label></category-label>
          <img src="https://images-fe.ssl-images-amazon.com/images/I/51-+tBY-5PL._AC_US160_.jpg">
          <p>
            <q-rating slot="subtitle" v-model="stars" :max="5" />
          </p>
        </q-card-media>
      </div>
      <div class="col-xs-8">
        <q-card-main class="card-content-container col-xs-8">
          <q-card-title slot="overlay" class="no-padding">
            Title
            <span slot="subtitle">Subtitle</span>
          </q-card-title>
          <p class="text-bold text-red">3000円 (3240円)</p>
          <q-btn color="positive" small outline icon="add_shopping_cart" class="full-width">購入する</q-btn>
          <q-card-actions class="col-xs-12 product-action-bar" align="around">
            <q-btn flat small color="primary"><q-icon name="details" />詳細を見る</q-btn>
            <q-btn flat small color="red"><q-icon name="favorite" />お気に入り</q-btn>
          </q-card-actions>
        </q-card-main>
      </div>
      <div class="col-xs-12">
        <q-card-actions>
          <p>
            <product-label label="test" color="primary"></product-label>
            <product-label label="test" color="primary"></product-label>
          </p>
        </q-card-actions>
      </div>
    </q-card>
    <q-card class="xs-hide">
      <q-card-media class="media-container">
        <img src="https://images-fe.ssl-images-amazon.com/images/I/51-+tBY-5PL._AC_US160_.jpg">
        <q-card-title slot="overlay">
          Title
          <span slot="subtitle">Subtitle</span>
        </q-card-title>
      </q-card-media>
      <q-card-main class="card-content-container">
        <p class="text-bold text-red">3000円 (3240円)</p>
        <p>
          <q-rating slot="subtitle" v-model="stars" :max="5" />
          <a>121人</a>
        </p>
        <p>
          <product-label label="test" color="primary"></product-label>
          <product-label label="test" color="primary"></product-label>
        </p>
        <q-btn color="positive" small icon="add_shopping_cart" class="full-width">購入する</q-btn>
      </q-card-main>
      <q-card-separator />
      <q-card-actions align="around" class="product-action-bar">
        <q-btn flat small color="primary"><q-icon name="details" />詳細を見る</q-btn>
        <q-btn flat small color="red"><q-icon name="favorite" />お気に入り</q-btn>
      </q-card-actions>
    </q-card>
    <q-card-separator />
  </div>
</template>

<script>
  import ProductLabel from './productLabel'
  import CategoryLabel from '@/shared/categoryLabel'
  export default {
    components: {
      ProductLabel,
      CategoryLabel
    },
    data () {
      return {
        stars: 3,
        lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~variables'
  .media-container
    padding: 16px
  .card-content-container
    padding: 8px
  .product-item p
    margin-bottom: 4px
  .product-action-bar
    padding-left 0
    padding-right 0
  @media screen and (max-width: $breakpoint-sm)
    .media-container
      padding: 8px
    .card-sp
      margin: 0
</style>