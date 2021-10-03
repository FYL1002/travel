<template>
    <div class="weekend-wrapper">
        <div class="weekend-title">周末去哪儿</div>
        <ul class="weekend-list">
            <router-link tag="li" class="weekend-item border-bottom" v-for="item of weekendList" :key="item.id" :to="item.linkUrl" >
                <div class="img-wrapper">
                    <img :src="item.imgUrl" alt="">
                </div>
                <div class="item-title">{{ item.title }}</div>
                <div class="item-des">{{ item.des }}</div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Weekend",
    data(){
        return {
            weekendList: [
                {
                    id: 1,
                    linkUrl: "https://piao.qunar.com/ticket/detail_14709.html#from=home_remen&in_track=qunar_djmp_pic_14709",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/ef/ef7167fdddb0f6da3.img.jpg_256x160_775adc4a.jpg",
                    title: "长隆野生动物世界",
                    des: "《爸爸去哪儿》拍摄地",
                },
                 {
                    id: 2,
                    linkUrl: "https://piao.qunar.com/ticket/detail_10462.html#from=home_remen&in_track=qunar_djmp_pic_10462",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2109/5f/5f399569a46896a9a3.water.jpg_256x160_af289ba7.jpg",
                    title: "深圳欢乐谷",
                    des: "丰富多彩的水陆游乐项目",
                },
                 {
                    id: 3,
                    linkUrl: "https://piao.qunar.com/ticket/detail_191026.html#from=home_remen&in_track=qunar_djmp_pic_191026",
                    imgUrl: "https://img1.qunarzz.com/sight/p0/2108/c9/c9b1feb9dd84cc1a3.img.jpg_256x160_4c163f2d.jpg",
                    title: "世界之窗",
                    des: "看全球名胜缩影环游世界",
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
.weekend-wrapper {
    width: 100%;
    .weekend-title {
        background: $greyColor;
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