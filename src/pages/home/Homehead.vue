<template>
    <div class="homeHead">
        <div class="head-left">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="head-search">
            <span class="iconfont">&#xe632;</span>
            <input type="text" class="inputBox" placeholder="输入城市/景点/游玩主题">
        </div>
        <div class="head-right">城市
            <span class="iconfont arrow-down">&#xe64a;</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HomeHead',

}
</script>

<style lang="scss" scoped>
@import '~@/assets/styles/mixins';
    .homeHead {
        display: flex;
        align-items: center;
        width: 100%;
        height: .86rem;
        line-height: .86rem;
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
            .iconfont.arrow-down{
                font-size: .26rem;
            }
        
        }
        
    }
        
</style>
