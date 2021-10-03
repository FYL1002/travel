<template>
  <div class="home">
    <home-head></home-head>
    <home-swiper></home-swiper>
    <icon-list></icon-list>
    <recommend></recommend>
    <weekend></weekend>

  </div>
</template>

<script>
// @ is an alias to /src
import HomeHead from '@/pages/home/HomeHead'
import HomeSwiper from '@/pages/home/HomeSwiper'
import IconList from '@/pages/home/IconList'
import Recommend from '@/pages/home/Recommend'
import Weekend from '../pages/home/Weekend.vue'


export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper,
    IconList,
    Recommend,
    Weekend
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