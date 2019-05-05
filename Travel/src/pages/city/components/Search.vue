<template>
    <div class="search">
     <input type="text" class="search-input" placeholder="输入城市名或拼音" />
    </div>
</template>
<script>
export default {
    name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.search
    height 0.72rem
    background $bgColor
    padding 0 .1rem
    .search-input
        text-align center
        height 0.62rem
        line-height .62rem
        width 100%
        border-radius .06rem
        color #666
        padding 0  .2rem
        box-sizing border-box
</style>