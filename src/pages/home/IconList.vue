<template>
    <ul class="icon-list">
        <router-link v-slot="{ href, navigate }" custom class="icon-item" v-for="item of iconList" :key="item.id" :to="item.linkUrl">
            <li @click="navigate" :href="href">
                <img :src="item.imgUrl" alt="">
                <span>{{item.text}}</span>
            </li>
        </router-link>
    </ul>
</template>

<script>
export default {
    name: "IconList",
    props: ["iconList"],
    data(){
        return{
          
        }
    }
}
</script>

<style lang="scss" scoped>
.icon-list {
    width: 100%;
    height: 3.6rem;
    display: flex;
    flex-wrap: wrap;
    overflow: hidden;
    .icon-item {
        width: 25%;
        height: 50%;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;

        img {
            height: 50%;
            padding-bottom: .1rem;
        }
    }
}
</style>