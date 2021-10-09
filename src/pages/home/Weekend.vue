<template>
    <div class="weekend-wrapper">
        <div class="weekend-title">周末去哪儿</div>
        <ul class="weekend-list">
            <router-link v-slot="{ navigate }" custom class="weekend-item border-bottom" v-for="item of weekendList" :key="item.id" :to="item.linkUrl" >
                <li @click="navigate" @keypress.enter="navigate" role="link">
                    <div class="img-wrapper">
                    <img :src="item.imgUrl" alt="">
                    </div>
                    <div class="item-title">{{ item.title }}</div>
                    <div class="item-des">{{ item.des }}</div>
                </li>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Weekend",
    props: {
        weekendList: Array
    }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
.weekend-wrapper {
    width: 100%;
    .weekend-title {
        background: $bgColorTitle;
        text-align: left;
        height: .62rem;
        line-height: .62rem;
        font-size: .3rem;
        text-indent: .2rem;
    }
    .weekend-list {
        width: 100%;
        .weekend-item {
            width: 100%;
            .img-wrapper {
                overflow: hidden;
                height: 0;
                padding-bottom: 2rem;
                img {
                    width: 100%;
                }
            }
            .item-title {
                @include ellipsis;
                font-size: .32rem;
                line-height: .56rem;
                text-align: left;
                text-indent: .2rem;
            }
             .item-des {
                @include ellipsis;
                font-size: .3rem;
                color: $fontColor;
                text-align: left;
                text-indent: .2rem;
                padding-bottom: .2rem;
            }
        }
    }
}
</style>