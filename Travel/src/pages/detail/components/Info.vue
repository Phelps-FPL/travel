<template>
  <div class="detail-info">
    <div class="detail-info-top">
      <div class="detail-info-score">
        <div>
          <span class="score">{{infos.score}}</span>
          <span class="text">分 很棒</span>
        </div>
        <p class="info-text">{{infos.comment}}条评论 {{infos.gonglve}}条攻略</p>
        <span class="iconfont right-arrow">&#xe630;</span>
      </div>
      <div class="detail-info-intro border-left">
        <div>景点简介</div>
        <p class="info-text">开放时间、小贴士</p>
        <span class="iconfont right-arrow">&#xe630;</span>
      </div>
    </div>
    <div class="detail-info-address border-top">
      <span class="iconfont address">&#xe649;</span>
      <span>{{infos.address}}</span>
      <span class="iconfont right-arrow">&#xe630;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailInfo',
  props: {
    infos: Object
  }
}
</script>

<style lang="stylus" scoped>
.detail-info
  background-color #fff
  padding 0.1rem 0.1rem 0 0.1rem
  .detail-info-top
    display flex
    flex-direction row
    padding 0.1rem
    .detail-info-score
      flex 1
      position relative
      .score
        color #ff8300
        font-size 0.4rem
      .text
        color #ff8300
        font-size 0.28rem
    .detail-info-intro
      flex 1
      position relative
      padding-left 0.3rem
    .info-text
      font-size 0.18rem
      color #999
      line-height 0.4rem
      margin-top 0.1rem
  .detail-info-address
    position relative
    padding 0.2rem 0.1rem
    .right-arrow
      right 0.25rem
    .address
      font-size 0.44rem
      color #999
      vertical-align middle
  .right-arrow
    font-size 0.36rem
    color #999
    position absolute
    right 0.15rem
    top 50%
    margin-top -0.18rem
</style>
