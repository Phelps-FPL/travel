<template>
    <div>
        <div class="item" v-for="(item,index) of list" :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                    {{item.title}}
            </div>
            <!-- 递归组件，自己调用自己 -->
            <div class="item-children" v-if="item.children">
                <detail-list :list = 'item.children'>
                    </detail-list>  
            </div> 
            <span class="money">￥{{item.money}}</span>
            <button class="btn">预定</button>
        </div>
    </div>  
</template>
 
<script>
export default {
    name: 'DetailList',
    props:{
        list: Array
    }
 
}
</script>

<style lang="stylus" scoped>
.item-title-icon
    position relative
    display inline-block
    left 0.1rem
    top 0.1rem
    width .36rem
    height .36rem
    background url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right .1rem
    background-size .4rem 3rem
.item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
.item-children
    padding 0 .3rem
    .money
        font-size 0.36rem
        color #ff8300
        position absolute
        top 0.3rem
        right 1.6rem
        display inline-block
    .btn
        width 1.2rem
        height 0.52rem
        line-height 0.52rem
        border-radius 0.1rem
        background-color #ff8300
        color #fff
        text-align center
        position absolute
        right 0.2rem
        top 0.2rem    
        display inline-block        
</style>