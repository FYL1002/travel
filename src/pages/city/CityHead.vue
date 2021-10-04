<template>
    <div class="head-wrapper">
        <router-link to="/">
            <span class="go-back iconfont">&#xe624;</span>
        </router-link>
        <span>城市选择</span>
    </div>
</template>

<script>
export default {
    name: "CityHead"
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.head-wrapper{
    height: .86rem;
    line-height: .86rem;
    background: $bgColor;
    color: #fff;
    font-size: .32rem;
    position: relative;

    .go-back{
        position: absolute;
        left: .2rem;
        top: 50%;
        transform: translateY(-50%);
        color: #fff;
    }
}
</style>