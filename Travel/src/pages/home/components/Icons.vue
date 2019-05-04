<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-img">
            <img class="icon-img-content"
            :src="item.imgurl" alt="">
            </div>
            <p class="icon-desc">{{item.desc}}</p>
        </div>
        </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
    name:'HomeIcons',
    data() {
        return {
            iconList:[
                {id:'0001',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',desc:'景点门票'},
                {id:'0002',imgurl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',desc:'一日游'},
                {id:'0003',imgurl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',desc:'深圳必游'},
                {id:'0004',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',desc:'海洋馆'},
                {id:'0005',imgurl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/bda58ffc3016edad84e656e8a94b0321.png',desc:'深圳动物园'},
                {id:'0006',imgurl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',desc:'深圳动物园'},
                {id:'0007',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/a6/6d97515091789602.png',desc:'世界之窗'},
                {id:'0008',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',desc:'玛雅水公园'},
                {id:'0009',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',desc:'东部华侨城'},


            ]
        }
    },
    computed:{
        pages () {
            const pages = []
            this.iconList.forEach((item,index)=>{
                const page = Math.floor(index / 8);
                if(!pages[page]){
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
    height 0
    padding-bottom 50%
.icon
    position relative
    float left
    height 0
    width 25%
    padding-bottom 25%
    overflow hidden
    .icon-img
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-img-content
            display block
            margin 0 auto 
            height 100%
    .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        line-height .44rem
        height .44rem
        color $darkTextColor     
        text-align center   
        ellipsis()
</style>