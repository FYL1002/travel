<template>
    <div class="home-swiper">
         <swiper :options="swiperOption" ref="mySwiper">
            <swiper-slide v-for="(item,index) of swiperData" :key="index">
                <a class="swiper-link" :href="item.linkUrl">
                    <img class="swiper-img" :src="item.imgUrl" alt="">
                </a>
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>           
        </swiper>
    </div>
</template>

<script>
export default {
    name: "HomeSwiper",
    data(){
        return{
            swiperOption: {              
                autoplay: 2000,
                loop: true,
                watchOverflow: true,
                initialSlide: 1,
                pagination: '.swiper-pagination',
                paginationClickable: true
            },
            swiperData:[
                {
                    linkUrl: '',
                    imgUrl: 'https://aecpm.alicdn.com/simba/img/TB1_JXrLVXXXXbZXVXXSutbFXXX.jpg'
                },
                {
                    linkUrl: '',
                    imgUrl: 'https://img.alicdn.com/imgextra/i2/O1CN01betoyt29ZbiEDexSS_!!6000000008082-0-tps-1130-500.jpg_q100.jpg_.webp'
                }
            ]
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