<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img"  :src="item.imgurl">
          </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop: true
      },
      swiperList:[
          {id:'0001',imgurl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/5daa78ddf9a3e3aca32195e079b9545d.jpg_750x200_3aeaa5c2.jpg'},
          {id:'0002',imgurl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/e0c5d91cb9b435518bb223b81b70874e.jpg_750x200_f2d5c66a.jpg'}
      ]
    };
  }
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