<template>
    <div class="search-wrapper">
        <input type="text" placeholder="输入城市名或拼音" />
    </div>
</template>

<script>
export default {
    name: "CitySearch"
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.search-wrapper{
    background: $bgColor;
    height: .72rem;
    line-height: .72rem;
    overflow: hidden;
    padding: 0 .16rem;

    input {
        width: 100%;
        box-sizing: border-box;
        padding: .04rem .1rem;
        border-radius: .06rem;
        color: #666;
        text-align: center;
    }
}
</style>