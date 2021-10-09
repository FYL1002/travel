<template>
    <div class="recommend-wrapper">
        <div class="recommend-title">热销推荐</div>
        <ul class="recommend-list">
            <router-link v-slot="{ navigate }" custom class="recommend-item border-bottom" v-for="item of recommendList" :key="item.id" :to="'/detail/' + item.id" >
                <li @click="navigate" @keypress.enter="navigate" role="link">
                    <div class="item-left">
                        <img :src="item.imgUrl" alt="">
                    </div>
                    <div class="item-right">
                        <div class="title">{{ item.title }}</div>
                        <div class="des">{{ item.des }}</div>
                        <div class="price"><span class="price-value">￥{{ item.price }}</span> 起</div>
                    </div>
                </li>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Recommend",
    props: {
        recommendList: Array
    },
    data(){
        return {
          
        }
    }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
.recommend-wrapper {
    width: 100%;
    .recommend-title {
        background: $bgColorTitle;
        text-align: left;
        height: .62rem;
        line-height: .62rem;
        font-size: .3rem;
        text-indent: .2rem;
    }
    .recommend-list {
        width: 100%;

        .recommend-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-sizing: border-box;
            height: 2rem;
            padding: .2rem;
            // border-bottom: .02rem solid #eee;
            overflow: hidden;
            .item-left {
                width: 35%;
                overflow: hidden;
                img {
                    width: 100%;
                    height: 1.7rem;
                }
            }
            .item-right {
                // flex: 1;
                width: 65%;
                text-align: left;
                padding: 0 .2rem;
                .title {
                    font-size: .32rem;
                    @include ellipsis;
                }
                .des {
                    @include ellipsis;
                    width: 100%;
                    color: #ccc;
                    margin: .3rem 0;
                }
                .price {
                    .price-value{
                        color: #ff9300;
                        font-weight: bold;
                    }
                }
            }
        }
    }
}
</style>