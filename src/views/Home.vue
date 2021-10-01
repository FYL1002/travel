<template>
  <div class="home">
    <home-head></home-head>
    <home-swiper></home-swiper>
    <icon-list></icon-list>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeHead from '@/pages/home/HomeHead'
import HomeSwiper from '@/pages/home/HomeSwiper'
import IconList from '@/pages/home/IconList'

export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper,
    IconList
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