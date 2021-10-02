<template>
    <div class="recommend-wrapper">
        <div class="recommend-title">热销推荐</div>
        <ul class="recommend-list">
            <router-link tag="li" class="recommend-item border-bottom" v-for="item of recommendList" :key="item.id" :to="item.linkUrl" >
                <div class="item-left">
                    <img :src="item.imgUrl" alt="">
                </div>
                <div class="item-right">
                    <div class="title">{{ item.title }}</div>
                    <div class="des">{{ item.des }}</div>
                    <div class="price"><span class="price-value">￥{{ item.price }}</span> 起</div>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Recommend",
    data(){
        return{
            recommendList:[
                {
                    id: 1,
                    linkUrl: "https://piao.qunar.com/ticket/detail_193517.html#from=home_remen&in_track=qunar_djmp_pic_193517",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/a4/a4aa0a34e9ec3de1a3.img.jpg_256x160_b198c86f.jpg",
                    title: "珠海长隆海洋王国",
                    des: "亚洲首台水上过山车 时空裂缝技术开发楼市房价考虑是否深刻理解发",
                    price: 200
                },
                {
                    id: 1,
                    linkUrl: "https://piao.qunar.com/ticket/detail_193517.html#from=home_remen&in_track=qunar_djmp_pic_193517",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/a4/a4aa0a34e9ec3de1a3.img.jpg_256x160_b198c86f.jpg",
                    title: "珠海长隆海洋王国",
                    des: "亚洲首台水上过山车 时空裂缝技术开发楼市房价考虑是否深刻理解发",
                    price: 200
                },
                {
                    id: 1,
                    linkUrl: "https://piao.qunar.com/ticket/detail_193517.html#from=home_remen&in_track=qunar_djmp_pic_193517",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/a4/a4aa0a34e9ec3de1a3.img.jpg_256x160_b198c86f.jpg",
                    title: "珠海长隆海洋王国",
                    des: "亚洲首台水上过山车 时空裂缝技术开发楼市房价考虑是否深刻理解发",
                    price: 200
                },
                {
                    id: 1,
                    linkUrl: "https://piao.qunar.com/ticket/detail_193517.html#from=home_remen&in_track=qunar_djmp_pic_193517",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/a4/a4aa0a34e9ec3de1a3.img.jpg_256x160_b198c86f.jpg",
                    title: "珠海长隆海洋王国",
                    des: "亚洲首台水上过山车 时空裂缝技术开发楼市房价考虑是否深刻理解发",
                    price: 200
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
.recommend-wrapper {
    width: 100%;
    .recommend-title {
        background: $greyColor;
        text-align: left;
        height: .6rem;
        line-height: .6rem;
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