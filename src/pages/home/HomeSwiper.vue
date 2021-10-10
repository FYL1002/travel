<template>
    <div class="home-swiper">
        <swiper :options="swiperOption" ref="mySwiper" v-if="swiperData.length">
            <swiper-slide v-for="(item,index) of swiperData" :key="index">
                <router-link class="swiper-link" :to="item.linkUrl">
                    <img class="swiper-img" :src="item.imgUrl" alt="">
                </router-link>
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>           
        </swiper>
    </div>
</template>

<script>
export default {
    name: "HomeSwiper",
    props: {
        swiperData: Array
    },
    data(){
        return{
            swiperOption: {              
                autoplay: 2000,
                loop: true,
                watchOverflow: true,
                initialSlide: 1,
                pagination: '.swiper-pagination',
                paginationClickable: true
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.home-swiper ::v-deep .swiper-pagination-bullet-active {
        background: #fff !important;
}
.home-swiper {
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 44%;
    background: #eee;

    .swiper-container {
        width: 100%;

        .swiper-link{
            display: block;
            width: 100%;
            height: 100%;

             .swiper-img {
                width: 100%;
                height: 100%;
            }
        }
    }
}
</style>