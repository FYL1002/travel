<template>
    <div class="detail-wrapper">
        <detail-head></detail-head>
        <detail-banner :imgs="imgs"></detail-banner>
        <div class="content">
            <basic-info></basic-info>
        </div>
        <div class="ticket-wrapper">
            <ticket-info :list="ticketList"></ticket-info>
        </div>
       

    </div>
</template>

<script>
import DetailHead from '@/pages/detail/DetailHead.vue'
import DetailBanner from '@/pages/detail/DetailBanner.vue'
import BasicInfo from '@/pages/detail/BasicInfo.vue'
import TicketInfo from '@/pages/detail/TicketInfo.vue'

export default {
    name: "Detail",
    data() {
        return {
            imgs: [
                "https://dimg04.c-ctrip.com/images/300416000000yy81fEF51_C_750_420_Q90.jpg",
                "https://img1.qunarzz.com/vs_ceph_b2c_001/3106b892-75ef-41e3-89ac-e588001650ed.jpg_r_640x420x95_b7f4452c.jpg",
                "https://img1.qunarzz.com/vs_ceph_b2c_001/e516d884-127f-477f-b69b-6fe038205658.jpg_r_640x420x95_51355563.jpg"
            ],
            ticketList: [
                {
                    title: "成人票",
                    children: [
                        {
                            title: "成人三馆联票",
                            children:[
                                {
                                    title: "长隆海洋世界"
                                }
                            ]
                        },
                        {
                            title: "成人五馆联票"
                        }
                    ]
                },
                {
                    title: "学生票",
                    children: [
                        {
                            title: "学生三馆联票"
                        },
                        {
                            title: "学生五馆联票"
                        }
                    ]
                },
                {
                    title: "儿童票",
                    children: [
                        {
                            title: "儿童全馆联票"
                        }
                    ]
                }
            ]
        }
    },
    components: {
        DetailHead,
        DetailBanner,
        BasicInfo,
        TicketInfo
    }
}
</script>

<style lang="scss" scoped>
.detail-wrapper {
    min-height: 16rem;
    background: #f5f5f5;
    overflow: hidden;
    .content {
        margin-top: -.4rem;
        background: #f5f5f5;
        overflow: hidden;
    }
    .ticket-wrapper {
            margin-top: .3rem;
    }
}
</style>