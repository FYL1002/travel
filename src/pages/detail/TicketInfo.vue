<template>
    <div class="ticket-info">
        <div class="ticket-type" v-for="(item, index) of list" :key="index">
            <img class="icon" :src="iconUrl" alt="">
            <span>{{ item.title }}</span>
            <div class="children-item">
                <ticket-info :list="item.children" v-if="item.children"></ticket-info>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "TicketInfo",
    props: {
        list: Array
    },
    data () {
        return {
            iconUrl: require("../../assets/img/star.jpeg")
        }
    }
}
</script>

<style lang="scss" scoped>
.ticket-info {
    background: #fff;
    text-align: left;
    .ticket-type {
        font-size: .3rem;
        .icon {
            display: inline-block;
            width: .6rem;
            height: .6rem;
            margin: 0 .1rem;
            padding-bottom: .1rem;
            box-sizing: border-box;
        }
        .children-item {
            padding: .1rem .4rem 0;
        }
    }
}
</style>