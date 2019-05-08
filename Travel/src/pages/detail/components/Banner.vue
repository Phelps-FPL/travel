<template>
    <div>
        <div class="banner" @click="handlebannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1904/1e/1e51b5ea32ee8033a3.water.jpg_600x330_8c20b7fb.jpg" alt="">
            <div class="banner-info">
                <div class="banner-title">深圳欢乐谷(AAAAA景区)</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe616;</span>54</div>
            </div>
        </div>
    <common-gallary :imgs = 'imgs' v-show="showGallary" @close='handleGallaryClose'></common-gallary>
    </div>
</template>
 
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
    name: 'DetailBanner',
    components: {
        CommonGallary
    },
    data () {
        return {
            showGallary: false,
            imgs:[
                'http://img1.qunarzz.com/sight/p0/1904/1e/1e51b5ea32ee8033a3.water.jpg_r_800x800_264c5e97.jpg',
                'http://img1.qunarzz.com/sight/p0/1904/ab/ab0a88533a0c1133a3.water.jpg_r_800x800_603aad94.jpg'
            ]
        }
    },
    methods: {
        handlebannerClick() {
            this.showGallary = true
        },
        handleGallaryClose() {
            this.showGallary = false
        }
    }
}
</script>

<style lang="stylus" scoped>
.banner
    position relative
    height 0
    overflow hidden
    padding-bottom 55%
    .banner-img
        width 100%
    .banner-info
        display flex
        position absolute
        left 0
        right 0
        bottom 0
        line-height .6rem
        color #fff
        background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
        .banner-title
            flex 1
        .banner-number
            padding 0 .4rem
            line-height .6rem
            border-radius .2rem
            background rgba(0,0,0,.8)
            font-size .24rem
            .banner-icon
                font-size .24rem
</style>