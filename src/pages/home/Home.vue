<template>
    <div>
        <home-header></home-header>

        <home-footer></home-footer>
    </div>
</template>
<script>
import HomeHeader from './components/header'
import HomeFooter from './components/footer'
export default{
    name:"Home",
    components:{
        HomeHeader: HomeHeader,
        HomeFooter: HomeFooter,
    }
}
</script>
<style>

</style>