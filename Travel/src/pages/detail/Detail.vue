<template>
    <div>
        <detail-banner :sightName = 'sightName' :bannerImg = 'bannerImg' :gallaryImgs='gallaryImgs'></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list = 'list'>l</detail-list>
        </div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
    name: 'Detail',
    components:{
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data() {
        return {
            sightName:'',
            bannerImg:'',
            gallaryImgs:[],
            list: [],
        }
    },
    methods: {
        getDetailInfo() {
            axios.get('/api/detail.json?',{
                params:{
                    id: this.$route.params.id
                }
            }).then(this.handleGetDateSucc)
        },
        handleGetDateSucc(res) {
            res = res.data
            if (res.data && res.ret) {
                const data = res.data
                this.sightName = data.sightName
                this.bannerImg = data.bannerImg
                this.gallaryImgs = data.gallaryImgs
                this.list = data.categoryList
                
            }
        }
    },
    // 通过keepalive做了缓存所以mounted只会执行一次 ,可以用activated,也可以在keep-alive上绑定exclude = '不缓存的组件如:detail 等'
    mounted () {
        this.getDetailInfo()
    }
}
</script>

<style lang="stylus" scoped>
.content
    height 50rem
</style>