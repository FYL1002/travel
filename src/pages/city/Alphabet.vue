<template>
    <ul class="alphabet-list">
        <li class="item" v-for="(item,key) of cities" :key="key">
            {{ key }}
        </li>
    </ul>
</template>

<script>
export default {
    name: "Alphabet",
    props: {
        cities: Object
    }
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.alphabet-list{
    overflow: hidden;
    position: fixed;
    width: .4rem;
    top: 1.58rem;
    bottom: 0;
    right: 0;
    left: auto;
    z-index: 999;
    display: flex;
    justify-content: center;
    flex-direction: column;
    .item {
        padding: .04rem 0;
        color: $bgColor;
    }
}
</style>