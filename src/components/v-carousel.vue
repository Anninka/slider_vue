<template>
  <div class="wrapper">
    <div class="v-carousel" :style="{ 'margin-left': '-' + (100 * currentSlideIndex) + '%'}">
      <v-carousel-item
        v-for="item in carousel_data"
        :key="item.id"
        :item_data="item"
      />
    </div>
    <button @click="prevSlide">Prev</button>
    <button @click="nextSlide">Next</button>
  </div>
</template>

<script>
import vCarouselItem from '@/components/v-carousel-item.vue'
import { enumNumberMember } from '@babel/types';

export default {
  name: 'v-carousel',
  components: {
    vCarouselItem
  },
  props: {
    carousel_data: {
      type: Array,
      default: () => []
    },
    interval: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      currentSlideIndex: 0
    }
  },
  methods: {
    prevSlide() {
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--
      }
    },
    nextSlide() {
      if (this.currentSlideIndex >= this.carousel_data.length - 1) {
        this.currentSlideIndex = 0;
      } else {
        this.currentSlideIndex++
      }
    }
  },
  mounted() {
    if (this.interval > 0) {
      let vm = this;
      setInterval(function () {
        vm.nextSlide()
      }, vm.interval)
    }
  }
}
</script>

<style scoped>
.wrapper {
  max-width: 800px;
  overflow: hidden;
  margin-inline: auto;
}

.v-carousel {
  display: flex;
  transition: all ease .5s;
}
</style>