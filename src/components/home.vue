<template>
  <q-layout>
    <router-link to="/products">
      <h6 class="text-center">
        <span class="positive text-red text-bold catch-frase">SAVE 20% TODAY</span> catch frase
      </h6>
    </router-link>
    <q-card class="no-margin bg-white">
      <q-card-media>
        <custom-carousel dots infinite autoplay :src="heroImages"></custom-carousel>
      </q-card-media>
      <q-card-main slot="overlay" class="text-primary text-bold text-center">
        FREE 1-2 DAY SHIPPING OVER $49!
        <q-icon name="thumb_up" />
      </q-card-main>
    </q-card>
    <scrollable-products></scrollable-products>
    <q-card-separator />
    <scrollable-products></scrollable-products>
    <q-card-separator />
    <scrollable-products></scrollable-products>
  </q-layout>
</template>

<script>
import ScrollableProducts from './shared/scrollableProducts'
import CustomCarousel from './shared/customCarousel'
export default {
  name: 'index',
  data () {
    return {
      heroImages: [
        'https://www.chewy.com/assets/img/_mobile/home/hero/veterinary-diets.20170224.jpg',
        'https://www.chewy.com/assets/img/_mobile/home/hero/american-brands.20170510.jpg',
        'https://www.chewy.com/assets/img/_mobile/home/hero/500-brands.2010406.jpg'
      ]
    }
  },
  components: {
    ScrollableProducts,
    CustomCarousel
  }
}
</script>

<style lang="stylus" scoped>
  @import '~variables'
  .catch-frase
    display: inline-block
    background-color: $warning
    padding: 8px
</style>
