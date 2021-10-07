<template>
    <div class="list-wrapper" ref="cityList">
        <div>
            <div class="area">
                <div class="title">
                    您的位置
                </div>
                <div class="content">
                    <div class="current-city"><div class="button-box">{{ $store.state.city }}</div></div>
                </div>
            </div>
            <div class="area">
                <div class="title">
                    热门城市
                </div>
                <div class="content">
                    <div class="current-city" v-for="item of hotCities" :key="item.id">
                        <div class="button-box" @click="handleCity(item.name)">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(city,key) of cities" :key="key" :ref="key">   
                <div class="title">
                    {{key}}
                </div>
                <div class="content all-city">
                    <ul class="city-list">
                        <li class="city-item" v-for="item of city" :key="item.id" @click="handleCity(item.name)">
                            {{item.name}}
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll';

export default {
    name: "CityList",
    props: {
        hotCities: Array,
        cities: Object,
        letter: String
    },
    data(){
        return {
            
        }
    },
    mounted(){
        this.scroll= new BScroll(this.$refs.cityList);  
        this.bus.$on("letterSelect", e=>{
            const el = this.$refs[e][0];
            if(el){
                this.scroll.scrollToElement(el);
            }
        }) 
    },
    updated(){
        this.scroll.refresh()
    },
    watch: {
        letter(){
            this.scroll.scrollToElement(this.$refs[this.letter][0]);
        }
    },
    methods: {
        handleCity(city){
            this.$store.commit("changeCity",city);
            this.$router.push("/");
        }
    },
    destroyed(){
        // 避免路由跳转多个组件重复监听,emit触发第一次 $on监听不到
        this.bus.$off("letterSelect");
    }

}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.list-wrapper {
    overflow: hidden;
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;

    .area{
        overflow: hidden;
        text-align: left;
        .title {
            height: .6rem;
            line-height: .6rem;
            padding: 0 .2rem;
            background: $bgColorTitle;
            color: #666;
            font-size: .26rem;
        }
        .content {
            overflow: hidden;
            padding: 0.1rem .6rem 0.1rem 0.1rem;

            .current-city {
                overflow: hidden;
                float: left;
                width: 33%;
                box-sizing: border-box;
                text-align: center;    

                .button-box {
                    box-sizing: border-box;
                    text-align: center;
                    padding: .1rem;
                    margin: .1rem;
                    border: .02rem solid #ccc;
                    border-radius: .06rem;
                }
            }
         
            &.all-city{
                padding: 0;
                .city-list {
                    overflow: hidden;
                    .city-item {
                        height: .6rem;
                        line-height: .6rem;
                        padding: 0 .4rem 0 .2rem;
                        border-bottom: 1px solid #eee;
                    }
                }
            }
        }
    }
}
</style>