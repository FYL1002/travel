<template>
    <div class="city-wrapper">
        <city-head></city-head>
    </div>
</template>

<script>
import CityHead from "../pages/city/CityHead.vue"

export default {
    name: "City",
    components: {
        CityHead
    }
}
</script>

<style lang="scss" scoped>
.city-wrapper {
    width: 100%;
}
</style>