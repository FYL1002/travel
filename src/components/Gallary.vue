<template>
    <div class="gallary-wrapper" @click="handleGallaryClick">
        <swiper :options="swiperOption" ref="Swiper">
            <swiper-slide v-for="(item,index) of imgs" :key="index">  
                <img class="swiper-img" :src="item" alt="">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>           
        </swiper>
    </div>
</template>

<script>
export default {
    name: "Gallary",
    props: {
        imgs: {
            type: Array,
            default() {
                return []
            }
        }
    },
    data() {
        return {
            swiperOption: {                
                initialSlide: 0,
                pagination: '.swiper-pagination',
                observe: true,
                observeParents: true,
            }
        }
    },
    methods: {
        handleGallaryClick (){
            this.$emit('close')
        }
    }
}
</script>

<style lang="scss" scoped>
.gallary-wrapper {
    width: 100%;
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background: #000;
    display: flex;
    align-items: center;
    overflow: hidden;
    z-index: 9999;

    .swiper-container{
        height: 6rem;
    
        .swiper-img {
            width: 100%;
            height: 100%;
            
        }

    }
}
</style>