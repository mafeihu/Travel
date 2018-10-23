<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :list="iconList"></home-icons>
        <home-recommend :list="recommendList"></home-recommend>
        <home-weekend :list="weekendList" ></home-weekend>
    </div>
</template>
<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/recommmend'
import HomeWeekend from './components/weekend'
import axios from 'axios'
export default{
    name:"Home",
    data(){
      return{
        city:'',
        swiperList:[],
        iconList:[],
        recommendList:[],
        weekendList:[],
      }
    },
    components:{
        HomeHeader: HomeHeader,
        HomeSwiper: HomeSwiper,
        HomeIcons: HomeIcons,
        HomeRecommend:HomeRecommend,
        HomeWeekend:HomeWeekend
    },
  methods:{
      getHomeInfo(){
        axios.get('/api/index.json').then(this.getHomeInfoSucc)
      },
    getHomeInfoSucc(res){
        res = res.data;
        if(res.ret && res.data){
          const data = res.data;
          console.log(data);
          //获取城市
          this.city = data.city;
          //获取轮播图
          this.swiperList =data.swiperList;
          //图标列表
          this.iconList = data.iconList;
          //推荐列表
          this.recommendList = data.recommendList
          //周末去哪儿
          this.weekendList = data.weekendList

        }
    }
  },
  //数据挂载的时候被调用
  mounted(){
      this.getHomeInfo();
  }
}
</script>
<style>
</style>
