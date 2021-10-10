<template>
    <div>
        <detail-head></detail-head>
        <detail-banner :imgs="imgs"></detail-banner>

    </div>
</template>

<script>
import DetailHead from '@/pages/detail/DetailHead.vue'
import DetailBanner from '@/pages/detail/DetailBanner.vue'

export default {
    name: "Detail",
    data() {
        return {
            imgs: [
                "https://dimg04.c-ctrip.com/images/300416000000yy81fEF51_C_750_420_Q90.jpg",
                "https://img1.qunarzz.com/vs_ceph_b2c_001/3106b892-75ef-41e3-89ac-e588001650ed.jpg_r_640x420x95_b7f4452c.jpg",
                "https://img1.qunarzz.com/vs_ceph_b2c_001/e516d884-127f-477f-b69b-6fe038205658.jpg_r_640x420x95_51355563.jpg"
            ]
        }
    },
    components: {
        DetailHead,
        DetailBanner
    }
}
</script>

<style lang="scss" scoped>

</style>