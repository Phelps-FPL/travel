<template>
    <div class="header">
        城市选择
        <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>
<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.header
    position relative
    overflow hidden
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #ffffff
    background $bgColor
    font-size .36rem
    .header-back
        left 0
        top 0
        position absolute
        width 0.64rem
        text-align center
        font-size  .4rem
        color #fff
</style>