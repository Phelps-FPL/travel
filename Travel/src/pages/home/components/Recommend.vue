<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:'HomeRecommend',
    data () {
        return {
            recommendList:[
                {id:'0001',imgUrl:'http://img1.qunarzz.com/sight/p0/1904/de/de517f86e9fd0d87a3.water.png_250x250_bc61af78.png',title:'世界之窗',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0002',imgUrl:'http://img1.qunarzz.com/sight/p0/1902/80/80d7d3ef350b7fffa3.water.jpg_250x250_7ac68b4a.jpg',title:'东部华侨城',desc:'来到深圳，你需要来这里签到'},
                {id:'0003',imgUrl:'http://img1.qunarzz.com/sight/p0/1904/de/de517f86e9fd0d87a3.water.png_250x250_bc61af78.png',title:'世界之窗',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0004',imgUrl:'http://img1.qunarzz.com/sight/p0/1902/80/80d7d3ef350b7fffa3.water.jpg_250x250_7ac68b4a.jpg',title:'东部华侨城',desc:'来到深圳，你需要来这里签到'},
                {id:'0005',imgUrl:'http://img1.qunarzz.com/sight/p0/1904/de/de517f86e9fd0d87a3.water.png_250x250_bc61af78.png',title:'世界之窗',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0006',imgUrl:'http://img1.qunarzz.com/sight/p0/1902/80/80d7d3ef350b7fffa3.water.jpg_250x250_7ac68b4a.jpg',title:'东部华侨城',desc:'来到深圳，你需要来这里签到'},
            ]
        }
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title
    line-height .8rem
    background #eee
    text-indent .2rem
    margin-top .2rem
.item
    display flex
    height 2.5rem
    overflow hidden
    .item-img
        width 1.7rem
        height 1.7rem
        padding .1rem
    .item-info
        flex 1
        padding .2rem
        min-width 0
        .item-title
            line-height .54rem
            font-size .32rem
            ellipsis()
        .item-desc
            line-height .4rem
            color #ccc
            ellipsis()
        .item-button
            line-height .44rem
            margin-top 0.16rem
            background #ff9300
            color #fff
            padding 0 .2rem
            border-radius .06rem
            
</style>