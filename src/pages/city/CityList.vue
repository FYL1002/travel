<template>
    <div class="list-wrapper">
        <div class="area">
            <div class="title">
                您的位置
            </div>
            <div class="content">
                <div class="current-city"><div class="button-box">深圳</div></div>
            </div>
        </div>
        <div class="area">
            <div class="title">
                热门城市
            </div>
            <div class="content">
                <div class="current-city"><div class="button-box">深圳</div></div>
                <div class="current-city"><div class="button-box">深圳</div></div>
                <div class="current-city"><div class="button-box">深圳</div></div>
                <div class="current-city"><div class="button-box">深圳</div></div>
            </div>
        </div>
        <div class="area">
            <div class="title">
                A
            </div>
            <div class="content all-city">
                <ul class="city-list">
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                </ul>
            </div>

            <div class="title">
                B
            </div>
            <div class="content all-city">
                <ul class="city-list">
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                </ul>
            </div>

            <div class="title">
                C
            </div>
            <div class="content all-city">
                <ul class="city-list">
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                    <li class="city-item">阿里</li>
                </ul>
            </div>

        </div>
    </div>
</template>

<script>
export default {
    name: "CityList"
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.list-wrapper {
    width: 100%;
    overflow: hidden;
    .area{
        overflow: hidden;
        text-align: left;
        .title {
            height: .6rem;
            line-height: .6rem;
            padding: 0 .2rem;
            background: $bgColorTitle;
            color: #666;
            font-size: .26rem;
        }
        .content {
            overflow: hidden;
            padding: 0.1rem .6rem 0.1rem 0.1rem;

            .current-city {
                overflow: hidden;
                float: left;
                width: 33%;
                box-sizing: border-box;
                text-align: center;    

                .button-box {
                    box-sizing: border-box;
                    text-align: center;
                    padding: .1rem;
                    margin: .1rem;
                    border: .02rem solid #ccc;
                    border-radius: .06rem;
                }
            }
         
            &.all-city{
                padding: 0;
                .city-list {
                    overflow: hidden;
                    .city-item {
                        height: .6rem;
                        line-height: .6rem;
                        padding: 0 .2rem;
                        border-bottom: 1px solid #eee;
                    }
                }
            }
        }
    }
}
</style>