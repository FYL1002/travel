<template>
  <div class="home">
    <home-head></home-head>
    <home-swiper :swiperData="swiperData"></home-swiper>
    <icon-list :iconList="iconList"></icon-list>
    <recommend :recommendList="recommendList"></recommend>
    <weekend :weekendList="weekendList"></weekend>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeHead from '@/pages/home/HomeHead'
import HomeSwiper from '@/pages/home/HomeSwiper'
import IconList from '@/pages/home/IconList'
import Recommend from '@/pages/home/Recommend'
import Weekend from '../pages/home/Weekend.vue'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper,
    IconList,
    Recommend,
    Weekend
  },
  data() {
    return {
      swiperData: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  created() {
    axios.get('/mock/home.json').then(
      res => {
        this.swiperData = res.data.data.swiperData;
        this.iconList = res.data.data.iconList;
        this.recommendList = res.data.data.recommendList;
        this.weekendList = res.data.data.weekendList
      },
      error => {
        console.log(error);
      }
    )
  }
  
}
</script>
<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>