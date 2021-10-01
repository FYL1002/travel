<template>
  <div class="home">
    <home-head></home-head>
    <home-swiper></home-swiper>
    <div style="overflow:hidden">1234士大夫</div>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeHead from '@/pages/home/HomeHead'
import HomeSwiper from '@/pages/home/HomeSwiper'

export default {
  name: 'Home',
  components: {
    HomeHead,
    HomeSwiper
  }
}
</script>
<style lang="scss" scoped>
.home{
  width: 100%;
  height: 100%;
  overflow: hidden;

}
</style>