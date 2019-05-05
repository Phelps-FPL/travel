<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="ShowSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id">
          <img class="swiper-img"  :src="item.imgUrl">
          </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeSwiper",
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop: true
      }
    };
  },
  computed: {
    ShowSwiper() {
      return this.list.length
    }
  },
};
</script>


<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background #fff
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 27.1%
    background #eee
    .swiper-img
        width 100%
</style>