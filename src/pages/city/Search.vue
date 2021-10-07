<template>
    <div class="search-container">
        <div class="search-wrapper">
            <input type="text" v-model="keyword" placeholder="输入城市名或拼音" />
        </div>
        <div class="search-result" v-show="keyword" ref="search">
            <ul>
                <li class="search-item border-bottom" v-for="item of resultList" :key="item.id" @click="handleCity(item.name)">{{item.name}}</li>
                <li class="search-item" v-show="hasNoData">没有找到匹配的数据！</li>
            </ul>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name: "CitySearch",
    props: {
        cities: Object
    },
    data(){
        return{
            keyword: '',
            resultList: [],
            timer: null
        }
    },
    mounted(){
        this.bscroll = new BScroll(this.$refs.search);
    },
    updated(){
        this.bscroll.refresh();
    },
    methods: {
        handleCity(city){
            this.$store.commit("changeCity",city);
            this.keyword = '';
            this.$router.push("/");
        }
    },
    computed: {
        hasNoData(){
            return !this.resultList.length;
        }
    },
    watch: {
        keyword(){
            if(this.timer){
                clearTimeout(this.timer);
                this.timer = null;
            }
            else{
                this.timer = setTimeout(() => {
                    this.resultList=[];
                    if(this.cities){
                        for (let item in this.cities){
                            this.cities[item].forEach(val => {
                                if(val.name.indexOf(this.keyword)>-1 || val.spell.indexOf(this.keyword)>-1){
                                    this.resultList.push(val);
                                }
                            });
                        }
                    }
                }, 30);
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import "~@/assets/styles/mixins";
.search-container {
    overflow: hidden;
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
    .search-result {
        position: absolute;
        top: 1.58rem;
        bottom: 0;
        right: 0;
        left: 0;
        z-index: 999;
        background: #eee;
        overflow: hidden;
        .search-item {
            padding: .1rem .2rem;
            background: #eee;
            text-align: left;
            background: #fff;
            color: #666;
        }
    }
}

</style>