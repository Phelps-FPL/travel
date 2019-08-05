<template>
  <div class="detail-comment">
    <div class="comment-title"><span>用户评论</span></div>
    <div class="comment-list">
      <div class="comment-item border-top"
           v-for="item of user"
           :key="item.userId">
        <div class="headline">
          <span class="username">{{item.userName}}</span>
          <span class="star">
            <star-icon :score="item.score"></star-icon>
          </span>
          <span class="date">{{item.date}}</span>
        </div>
        <div class="details">
          {{item.comments}}
        </div>
        <div class="detail-imgs"
             @click="switchCommonGallary">
          <div class="detail-img"
               @click="handleImgClick(item.imgs)"
               v-for="(url,index) of item.imgs"
               :key="index">
            <img class="img"
                 :src="url"
                 alt="">
          </div>
          <div class="detail-img-total">共{{item.imgs.length}}张</div>
        </div>
      </div>
    </div>
    <fade-animation>
      <preview-image :imgs="CommonGallary"
                     @close="switchCommonGallary"
                     v-show="isShow"></preview-image>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
import StarIcon from 'common/star/Star'
export default {
  name: 'DetailComment',
  props: {
    user: Array
  },
  components: {
    CommonGallary,
    FadeAnimation,
    StarIcon
  },
  data () {
    return {
      isShow: false,
      CommonGallary: []
    }
  },
  methods: {
    switchCommonGallary () {
      this.isShow = !this.isShow
    },
    handleImgClick (res) {
      this.CommonGallary = res
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.detail-comment
  background-color #fff
  margin-top 0.2rem
  .comment-title
    padding 0.3rem 0.2rem
    font-size 0.32rem
    span
      border-left 0.08rem solid $bgColor
      padding-left 0.15rem
  .comment-list
    overflow hidden
    .comment-item
      padding 0.2rem
      .headline
        padding 0.1rem 0
        overflow hidden
        .username
          font-size 0.28rem
          color #000
          float left
        .star
          float left
          padding 0 0.2rem
        .date
          float right
          font-size 0.28rem
          color #999
      .details
        padding 0.1rem 0
        color #666666
        line-height 1.5
      .detail-imgs
        overflow hidden
        position relative
        height 1.8rem
        .detail-img
          float left
          width 33.3%
          box-sizing border-box
          padding 0.1rem
          .img
            display block
            width 100%
            height 1.6rem
        .detail-img-total
          position absolute
          right 0.1rem
          bottom 0.2rem
          padding 0.1rem
          font-size 0.24rem
          color #fff
          border-radius 0.1rem 0 0 0.1rem
          background-color rgba(0, 0, 0, 0.2)
</style>
