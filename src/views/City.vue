<template>
    <div class="city-wrapper">
        <city-head></city-head>
        <city-search></city-search>
    </div>
</template>

<script>
import CityHead from "../pages/city/CityHead.vue"
import CitySearch from "../pages/city/Search.vue"

export default {
    name: "City",
    components: {
        CityHead,
        CitySearch
    }
}
</script>

<style lang="scss" scoped>
.city-wrapper {
    width: 100%;
}
</style>