<template>
    <div class="city-wrapper">
        <city-head></city-head>
        <city-search></city-search>
        <city-list></city-list>
    </div>
</template>

<script>
import CityHead from "../pages/city/CityHead.vue"
import CitySearch from "../pages/city/Search.vue"
import CityList from "../pages/city/CityList.vue"

export default {
    name: "City",
    components: {
        CityHead,
        CitySearch,
        CityList
    }
}
</script>

<style lang="scss" scoped>
.city-wrapper {
    width: 100%;
}
</style>