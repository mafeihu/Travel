<template>
    <div class="swiper">
        <swiper :options="swiperOption" ref="mySwiper">
            <swiper-slide v-for="item of swiperList">
                <img class="swiper-img" :src="item.imgUrl" :key="item.id"/>
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default{
    name:"HomeSwiper",
    data(){
        return{
            swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
            },
            swiperList:[
                {
                    id:'0001',
                    imgUrl:'https://img1.qunarzz.com/vc/2f/8e/51/cb4d31b360c836f7d1bbe83c13.jpg'
                },{
                    id:'0002',
                    imgUrl:'https://img1.qunarzz.com/vc/a5/e0/64/c6bd8680fb67247db15df6057b.jpg'
                }
            ]
        }
    }
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .swiper >>> .swiper-pagination-bullet-active
        background: #fff !important
    .swiper
        width:100%
        height:0
        padding-bottom:31.25%
        .swiper-img
            width:100%
</style>