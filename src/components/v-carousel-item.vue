<template>
  <div class="v-carousel-item">
    <img :src=" require('../assets/images/' + item_data.img) " alt="" width="800">
  </div>
</template>

<script>
export default {
  name: 'v-carousel-item',
  props: {
    item_data: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {}
  }
}
</script>

<style scoped>

</style>