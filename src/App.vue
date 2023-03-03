<template>
  <div id="app">
    <v-carousel
      :carousel_data="sliderItems"
      :interval="2000"
    />
  </div>
</template>

<script>
import vCarousel from '@/components/v-carousel.vue'

export default {
  name: 'app',
  components: {
    vCarousel
  },
  data() {
    return {
      sliderItems: [
        { id: 1, name: 'img1', img: '1.jpg' },
        { id: 2, name: 'img2', img: '2.jpg' },
        { id: 3, name: 'img3', img: '3.jpg' },
        { id: 4, name: 'img4', img: '4.jpg' },
        { id: 5, name: 'img5', img: '5.jpg' },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
