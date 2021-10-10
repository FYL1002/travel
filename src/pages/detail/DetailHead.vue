<template>
    <div class="header">
        <span class="iconfont back-icon">&#xe624;</span>
        <span class="text">标题</span>
    </div>
</template>

<script>
export default {
    name: "DetailHead"
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
    background: $bgColor;
    text-align: left;
    display: none;

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
    .text {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);

    }

}
</style>