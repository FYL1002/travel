<template>
    <div class="homeHead">
        <div class="head-left">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="head-search">
            <span class="iconfont">&#xe632;</span>
            <input type="text" class="inputBox" placeholder="输入城市/景点/游玩主题">
        </div>
        <router-link to="/city">
            <div class="head-right">{{city}}
                <span class="iconfont arrow-down">&#xe64a;</span>
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
    name: 'HomeHead',
    props: {
        city: String
    }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
    .homeHead {
        display: flex;
        align-items: center;
        width: 100%;
        height: $headHeight;
        line-height: $headHeight;
        background: $bgColor;
        color: #fff;

        .head-left {
            width: .64rem;
            
        }
        .head-search {
            flex:1;
            display: flex;
            align-items: center;
            height: .64rem;
            line-height: .64rem;
            background: #fff;
            color: #ccc;
            border-radius: .1rem;
            margin: 0 .12rem;
            padding: 0 .2rem;
            .inputBox {
                box-sizing: border-box;
                flex: 1;
                padding: 0 .06rem;
            }
        }
        .head-right {
            width: 1.2rem;
            color: #fff;
            .iconfont.arrow-down{
                font-size: .26rem;
            }
        }   
    }
</style>
