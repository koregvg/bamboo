<template>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="urlObj in img"
                 :style="{ backgroundImage: 'url(' + urlObj.url + ')' }"></div>
        </div>
        <!-- Add Pagination -->
        <div class="swiper-pagination swiper-pagination-white"></div>
    </div>
</template>

<script>
    import Swiper from 'swiper';
    import 'swiper/dist/css/swiper.min.css';
    export default {
        props: ['img'],
        mounted() {
            var swiper = new Swiper('.swiper-container', {
                pagination: '.swiper-pagination',
                paginationClickable: true,
                centeredSlides: true,
                autoplay: 2500,
                autoplayDisableOnInteraction: false
            });
        }
    }
</script>

<style lang="less" scoped>

</style>