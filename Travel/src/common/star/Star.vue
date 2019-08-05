<template>
  <div class="stars">
    <template v-for="(value,index) of stars">
      <span class="iconfont"
            :class="value === 1 ? 'selected' : ''"
            :key="index">&#xe714;</span>
    </template>
    <span class="star-score">{{score}}</span>
  </div>
</template>

<script>
export default {
  name: 'Star',
  props: {
    score: Number
  },
  computed: {
    stars () {
      // 处理评分 转换成数组 4.9 ==> [1,1,1,1,0]
      if (!isNaN(this.score)) {
        const stars = []
        for (let i = 1; i <= 5; i++) {
          if (i <= this.score) {
            stars.push(1)
          } else {
            stars.push(0)
          }
        }
        return stars
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.stars
  overflow hidden
  .iconfont
    float left
    font-size 0.28rem
    color #999999
    margin 0 2px
    vertical-align middle
  .iconfont.selected
    color #fcb636
  .star-score
    font-size 0.26rem
    vertical-align middle
    margin-left 0.05rem
</style>
