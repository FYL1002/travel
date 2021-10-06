<template>
    <ul class="alphabet-list">
        <li class="item" v-for="(item,key) of cities" 
        :key="key"
        :ref="key" 
        @click="handleSelect"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >
            {{ key }}
        </li>
    </ul>
</template>

<script>
export default {
    name: "Alphabet",
    props: {
        cities: Object
    },
    data(){
        return{
            touchStatus: false,
            letters: [],
            timer: null
        }
    },
    updated(){
        this.startY = this.$refs['A'][0].offsetTop;
         for(let i in this.cities){
            this.letters.push(i);
        }
    },
    methods: {
        handleSelect(e){
            let letter = e.target.innerText;
            this.bus.$emit("letterSelect",letter)
        },
        handleTouchStart(){
            this.touchStatus = true
        },
        handleTouchMove(e){
            if(this.touchStatus){
                if(this.timer){
                    clearTimeout(this.timer);
                    this.timer = null;
                }
                else{
                        this.timer = setTimeout(() => {
                        const touchY = e.touches[0].clientY-79;
                        const moveLength= Math.floor((touchY-this.startY)/18);
                        if(moveLength && moveLength>0 && moveLength<this.letters.length){                         
                            this.$emit('change',this.letters[moveLength]);  
                        }
                        }, 20);
                    }
            }
        },
        handleTouchEnd(){
            this.touchStatus = false
        }
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
    z-index: 99;
    display: flex;
    justify-content: center;
    flex-direction: column;
    .item {
        padding: .04rem 0;
        color: $bgColor;
    }
}
</style>