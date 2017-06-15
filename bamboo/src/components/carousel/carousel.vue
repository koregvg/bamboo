<template>
    <div class="carousel-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="urlObj in img"
                 :style="{ backgroundImage: 'url(' + urlObj.url + ')' }"></div>
        </div>
        <!-- Add Arrows -->
        <div class="swiper-button-next"></div>
        <div class="swiper-button-prev"></div>
    </div>
</template>

<script>
    import Swiper from 'swiper';
    import 'swiper/dist/css/swiper.min.css';
    export default {
        props: {
            img:{
                type: Object,
                required: false,
                default: ''
            },
            number: { // 项目ID
                type: Number,
                required: false,
                default: 3
            }
        },
        mounted() {
            var swiper = new Swiper('.carousel-container', {
                nextButton: '.swiper-button-next',
                prevButton: '.swiper-button-prev',
                slidesPerView: this.number,
            });
        }
    }
</script>

<style lang="less" scoped>

</style>