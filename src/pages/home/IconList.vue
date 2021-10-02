<template>
    <ul class="icon-list">
        <router-link tag="li" class="icon-item" v-for="item of iconList" :key="item.id" :to="item.linkUrl">
            <img :src="item.imgUrl" alt="">
            <span>{{item.text}}</span>
        </router-link>
    </ul>
</template>

<script>
export default {
    name: "IconList",
    data(){
        return{
            iconList:[
                {
                    id: 1,
                    linkUrl: "/",
                    imgUrl: "https://s.qunarzz.com/homenode/images/touchheader/hotel.png",
                    text: "酒店"
                },
                {
                    id: 2,
                    linkUrl: "",
                    imgUrl: "https://s.qunarzz.com/homenode/images/touchheader/flight.png",
                    text: "机票"
                },
                {
                    id: 3,
                    linkUrl: "",
                    imgUrl: "https://s.qunarzz.com/homenode/images/touchheader/train.png",
                    text: "火车票"
                },
                {
                    id: 4,
                    linkUrl: "",
                    imgUrl: "https://s.qunarzz.com/homenode/images/touchheader/package.png",
                    text: "度假"
                },
                {
                    id: 5,
                    linkUrl: "",
                    imgUrl: "https://s.qunarzz.com/homenode/images/touchheader/piao.png",
                    text: "景点门票"
                },
                {
                    id: 6,
                    linkUrl: "",
                    imgUrl: "https://picbed.qunarzz.com/377db8cb2143aebf01869c9baad3d325.png",
                    text: "汽车票船票"
                },
                {
                    id: 7,
                    linkUrl: "",
                    imgUrl: "https://picbed.qunarzz.com/1316dc82d1ce6259686d5a68880e5a9d.png",
                    text: "攻略"
                },
                {
                    id: 8,
                    linkUrl: "",
                    imgUrl: "https://picbed.qunarzz.com/ae617a31e0bd5803d76918b817f6d942.png",
                    text: "自由行"
                }
            ]
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