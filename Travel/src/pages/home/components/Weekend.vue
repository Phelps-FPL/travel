<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-warpper">
                    <img class="item-img" :src="item.imgUrl" alt="">
                    </div>               
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:'HomeWeekend',
    data () {
        return {
            recommendList:[
                {id:'0001',imgUrl:'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',title:'清远周边游',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0002',imgUrl:'http://img1.qunarzz.com/sight/source/1602/88/bf120edeaea383.jpg_r_640x214_f8591f7b.jpg',title:'欢乐长隆',desc:'世界欢乐汇聚长隆，这里拥有多个大型游乐设备和精彩的演出，和小伙伴们一起感受刺激的体验'},
                {id:'0003',imgUrl:'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',title:'清远周边游',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0004',imgUrl:'http://img1.qunarzz.com/sight/source/1602/88/bf120edeaea383.jpg_r_640x214_f8591f7b.jpg',title:'欢乐长隆',desc:'世界欢乐汇聚长隆，这里拥有多个大型游乐设备和精彩的演出，和小伙伴们一起感受刺激的体验'},
                {id:'0005',imgUrl:'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',title:'清远周边游',desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'},
                {id:'0006',imgUrl:'http://img1.qunarzz.com/sight/source/1602/88/bf120edeaea383.jpg_r_640x214_f8591f7b.jpg',title:'欢乐长隆',desc:'世界欢乐汇聚长隆，这里拥有多个大型游乐设备和精彩的演出，和小伙伴们一起感受刺激的体验'},
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
.item-img-warpper
    overflow hidden
    height 0
    padding-bottom 33.9%
    .item-img
        width 100% 
.item-info
    padding .2rem
    .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
    .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
</style>