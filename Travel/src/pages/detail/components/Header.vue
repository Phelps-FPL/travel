<template>
    <div>
        <!-- 头部返回箭头 -->
        <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
            <div class="iconfont header-abs-back">&#xe624;</div>
        </router-link>
        <!-- 顶部渐变固定栏 -->
        <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">                
        <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
        </router-link>
        景点详情
        </div>
    </div>
</template>
 
<script>
export default {
    name: 'DetailHeader',
    data() {
        return {
            showAbs: true,
            opacityStyle:{
                opacity:0
            }
        }
    },
    methods: {
        handleScroll() {
            console.log(scroll)
            const top  = document.documentElement.scrollTop
            if(top > 60){
                let opacity = top / 140   
                opacity = opacity > 1 ? 1 : opacity
                //当键值相同，可以只写一个值
                this.opacityStyle = { opacity } //{opacity : 'opacity'}
                this.showAbs = false
            }else{
                this.showAbs = true
            }
        }
    },
    activated () {
        window.addEventListener('scroll',this.handleScroll)
    },
    //对全局事件的解绑
    deactivated() {
        window.removeEventListener('scroll',this.handleScroll)
    },
}

</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.header-abs
    position absolute
    left 0.2rem
    top 0.2rem
    width 0.8rem
    height 0.8rem
    line-height .8rem
    text-align center
    border-radius .4rem 
    background rgba(0,0,0,.8)
    .header-abs-back
        font-size .4rem
        color  #fff
.header-fixed
    position fixed
    left 0
    top 0
    right 0
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #ffffff
    background $bgColor
    font-size .36rem
    .header-fixed-back
        left 0
        top 0
        position absolute
        width 0.64rem
        text-align center
        font-size  .4rem
        color #fff
</style>