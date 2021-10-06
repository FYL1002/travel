<template>
    <div class="city-wrapper">
        <city-head></city-head>
        <city-search :cities="cities"></city-search>
        <city-list :cities="cities" :hotCities="hotCities" :letter="letter"></city-list>
        <alphabet :cities="cities" @change="handleTouchMove"></alphabet>
    </div>
</template>

<script>
import CityHead from "../pages/city/CityHead.vue"
import CitySearch from "../pages/city/Search.vue"
import CityList from "../pages/city/CityList.vue"
import Alphabet from "../pages/city/Alphabet.vue"
import axios from "axios"
import Vue from 'vue'

Vue.prototype.bus = new Vue()

export default {
    name: "City",
    components: {
        CityHead,
        CitySearch,
        CityList,
        Alphabet
    },
    data(){
        return {
            hotCities: [],
            cities: {},
            letter: ''
        }
    },
    mounted(){
        this.getData();
    },
    methods: {
        getData (){
            axios.get('/mock/city.json').then(
                res=>{
                    res = res.data;
                    if(res.ret && res.data){
                        const data = res.data;
                        this.hotCities = data.hotCities;
                        this.cities = data.cities;     
                    }                  
                },
                error=>{
                    console.log(error);
                }
            )
        },
        handleTouchMove(e){
            this.letter = e;
        }
    }
}
</script>

<style lang="scss" scoped>
.city-wrapper {
    width: 100%;
    overflow: hidden;
}
</style>