<template>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="urlObj in listImg"
                 :style="{ backgroundImage: 'url(' + urlObj.url + ')' }"></div>
        </div>
        <div class="swiper-pagination swiper-pagination-white"></div>
    </div>
</template>

<script>
    import Swiper from 'swiper';

    export default {
        props: {
            listImg: { // 项目ID
                type: Array,
                required: false,
                default: ''
            }
        },
        mounted() {
            console.log('mounted', this);
            let swiper = new Swiper('.swiper-container', {
                pagination: '.swiper-pagination',
                paginationClickable: true,
                loop: true,
                speed: 600,
                autoplay: 3000,
                onTouchEnd: function () {
                    swiper.startAutoplay()
                }
            });
        },
        methods() {

        }
    }
</script>

<style lang="less" scoped>
    @import '../lib/swiper/swiper.min.css';
</style>