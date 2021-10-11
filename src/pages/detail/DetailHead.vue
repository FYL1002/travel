<template>
    <div class="header" :class="{'scroll-head':scrollStyle}">
        <router-link v-slot="{ navigate }" custom to="/">
            <span @click="navigate" class="iconfont back-icon">&#xe624;</span>
        </router-link>
        <span class="title-text">景点详情</span>
    </div>
</template>

<script>
export default {
    name: "DetailHead",
    data() {
        return {
            scrollStyle: false
        }
    },
    mounted() {
        window.addEventListener("scroll",this.handlScroll)
    },
    methods: {
        handlScroll() {
            let scrollTop = document.documentElement.scrollTop;
            if(scrollTop>40){
                this.scrollStyle = true
            }
            else{
                this.scrollStyle = false
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.header {
    width: 100%;
    height: .88rem;
    line-height: .88rem;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: transparent;
    text-align: left;
    z-index: 999;
    .back-icon {
        display: inline-block;
        width: .6rem;
        height: .6rem;
        line-height: .6rem;
        text-align: center;
        background: rgba(0,0,0,0.5);
        color: rgb(255, 255, 255);
        font-size: .32rem;
        border-radius: 50%;
        margin-left: .2rem;
    }
    .title-text {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        color: #fff;
        font-size: .32rem;
        opacity: 0;
    }
    &.scroll-head {
        background: $bgColor;
        transition: background-color 0.6s linear;
        .back-icon {
            background: transparent;
            border-radius:initial;
        }
        .title-text {
            opacity: 1;
            transition: opacity 0.6s linear;
        }
    }
}
</style>