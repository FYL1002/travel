<template>
    <div class="basic-info">
        <div class="price-info">
            <span class="price-value">￥2000</span>起/人
        </div>
        <div class="title-info">
            自由行 云南丽江+香格里拉+梅里雪山6日5晚自由行☆独立用车☆希尔顿酒店☆双雪山体验
        </div>
        <ul class="point">
            <li class="item">云南旅游组合险</li>
            <li class="item">丽江进丽江出</li>
            <li class="item">独立用车</li>
            <li class="item">纯玩0购物</li>
            <li class="item">网红景点打卡</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "BasicInfo"
}
</script>

<style lang="scss" scoped>
.basic-info {
    background: #fff;
    border-top-left-radius: .4rem;
    border-top-right-radius: .4rem;
    display: inline-block;
    padding: .3rem .2rem .2rem;
    text-align: left;
    .price-info {
        color: #9e9e9e;
        font-size: .28rem;
        .price-value {
            color: #ff8300;
            font-size: .44rem;
        }
    }
    .title-info{
        font-size: .36rem;
        padding: .2rem 0;
    }
    .point {
        .item {
            float: left;
            padding: .1rem;
            &::before {
                content: "";
                width: .2rem;
                height: .2rem;
                background: orange;
                border-radius: 50%;
                display: inline-block;
                margin-right: .1rem;
        
            }
        }
    }
}
</style>