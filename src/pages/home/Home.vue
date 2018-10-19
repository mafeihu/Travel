<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <div>test</div>
    </div>
</template>
<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
export default{
    name:"Home",
    components:{
        HomeHeader: HomeHeader,
        HomeSwiper: HomeSwiper,
    }
}
</script>
<style>

</style>