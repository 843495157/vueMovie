<template>
    <Carousel v-model="value1" :autoplay="setting.autoplay" :autoplay-speed="setting.autoplaySpeed" :dots="setting.dots"
        :radius-dot="setting.radiusDot" :trigger="setting.trigger" :arrow="setting.arrow">
        <CarouselItem v-for="item in imgList" :key="item.id">
            <router-link class="demo-carousel"  target="_blank"  :to="'/detail/' + item.id" ><img :src=item.src /></router-link>
        </CarouselItem>
<!-- @click="goDetail(item.id)" -->
    </Carousel>
</template>
<script>
    import s1 from "../assets/1.jpg"
    import s2 from "../assets/2.jpg"
    import s3 from "../assets/3.jpg"
    import s4 from "../assets/4.jpg"
    import s5 from "../assets/5.jpg"
    import s6 from "../assets/6.jpg"
    import s7 from "../assets/7.jpg"
    import s8 from "../assets/8.jpg"
    import s9 from "../assets/9.jpg"
    import $ from 'jquery'
    export default {
        data() {
            return {
                value1: 0,
                setting: {
                    autoplay: true,
                    autoplaySpeed: 2000,
                    dots: 'inside',
                    radiusDot: false,
                    trigger: 'click',
                    arrow: 'hover',

                },
                // imgList:["../src/images/1.jpg","../src/images/2.jpg","../src/images/3.jpg","../src/images/4.jpg","../src/images/5.jpg","../src/images/6.jpg","../src/images/7.jpg","../src/images/8.jpg","../src/images/9.jpg",]
                //                imgList: [s1, s2, s3, s4, s5, s6, s7, s8, s9]
                imgList: [
                    { id: 1, src: s1 },
                    { id: 2, src: s2 },
                    { id: 3, src: s3 },
                    { id: 4, src: s4 },
                    { id: 5, src: s5 },
                    { id: 6, src: s6 },
                    { id: 7, src: s7 },
                    { id: 8, src: s8 },
                    { id: 9, src: s9 }]
            }
        },
        mounted() {

            $(".demo-carousel img").css("height", window.innerHeight)
            $(window).resize(function () {
                $(".demo-carousel img").css("height", window.innerHeight)
            });
        },
        methods: {
            // goDetail(id) {
            //     this.$router.push('/detail/' + id)
            // }
        }
    }
</script>
<style scoped>
    .demo-carousel {
        cursor: pointer;
        display: block;
    }

    .demo-carousel img {
        width: 100%;

    }

    .ivu-carousel {
        margin-top: -64px;
    }
</style>