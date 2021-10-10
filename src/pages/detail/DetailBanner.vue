<template>
    <div>
        <div class="banner-wrapper" @click="handleBannerClick">
            <img :src="imgs[0]" alt="">
        </div>
        <gallary :imgs="imgs" v-if="showGallary" @close="closeGallary"></gallary>
    </div>
    
</template>

<script>
import Gallary from '@/components/Gallary'
export default {
    name: "DetailBanner",
    components: {
        Gallary
    },
    props: {
        imgs: {
            type: Array,
            default() {
                return []
            }
        }
    },
    data(){
        return {
            showGallary: false
        }
    },
    methods: {
        handleBannerClick() {
            this.showGallary = true;
        },
        closeGallary() {
            this.showGallary = false;
        }
    }
}
</script>

<style lang="scss" scoped>
.banner-wrapper {
    width: 100%;
    height: 0;
    padding-bottom: 4.2rem;
    background: #bbb;
    overflow: hidden;
    
    img {
        width: 100%;
    }
}
</style>