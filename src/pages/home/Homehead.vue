<template>
    <div class="homeHead">
        <div class="head-left">24</div>
        <div class="head-search">
            <input type="text" class="inputBox" placeholder="请输入">
        </div>
        <div class="head-right">城市</div>
    </div>
</template>

<script>
export default {
    name: 'HomeHead',

}
</script>

<style lang="scss" scoped>
    $width:100px;
    .homeHead {
        display: flex;
        align-items: center;
        width: 100%;
        height: .86rem;
        line-height: .86rem;
        background: #00bcd4;
        color: #fff;

        .head-left {
            width: .64rem;
            
        }
        .head-search {
            flex:1;
            height: .64rem;
            line-height: .64rem;
            background: #fff;
            border-radius: .1rem;
            margin: 0 .12rem;
            .inputBox {
                box-sizing: border-box;
                width: 100%;
                padding: 0 .06rem;
                
            }
        }
        .head-right {
            width: 1.2rem;
            
        
        }
        
    }
        
</style>
