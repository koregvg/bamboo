<template>
    <section class="page-index">
        <header-bar
                :height="50"
                bgColor="rgba(0,0,0,0.5)"
                :listItem="[
                {text:'首页',href:'#',value:0},
                {text:'公司项目',href:'#',value:1},
                {text:'人才培养',href:'#',value:2},
                {text:'新闻资讯',href:'#',value:3},
                {text:'成功案例',href:'#',value:4},
                {text:'关于我们',href:'#',value:5},
                {text:'联系我们',href:'#',value:6},
                ]"
        >
            <div slot="left-content">
                我是左侧的内容
            </div>
        </header-bar>
        <slider
                :img="listImg"
        >
        </slider>
        <carousel
                :img="logoImg"
        >
        </carousel>
        <scaler
                :width="100"
                :height="100"
        >
            <div slot="content" class="slot">
                <img :src="imgSrc">
            </div>
        </scaler>
        <box-gallery
                :width="100"
                :height="100"
        >
        </box-gallery>
    </section>
</template>

<script>
    import headerBar from '../../header-bar/header-bar.vue'
    import slider from '../../slider/slider.vue'
    import carousel from '../../carousel/carousel.vue'
    import scaler from '../../scaler/scaler.vue'
    import boxGallery from '../../box-gallery/box-gallery.vue'
    import img1 from './img/banner1.png'
    import img2 from './img/banner2.jpg'
    import img3 from './img/banner3.jpg'
    import img4 from './img/landscape.jpg'

    export default {
        name: 'index',
        data () {
            return {
                listImg: [{
                    url: img1
                }, {
                    url: img2
                }, {
                    url: img3
                }],
                logoImg:[{
                    url: img1
                }, {
                    url: img2
                }, {
                    url: img3
                }, {
                    url: img1
                }, {
                    url: img2
                }, {
                    url: img3
                }],
                imgSrc: img4
            }
        },
        components: {
            headerBar,
            slider,
            carousel,
            scaler,
            boxGallery
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
    .page-index {
        .header-bar {
            z-index: 100;
            position: fixed;
            .left-content {
                font-size: 16px;
                margin-left: 30px;
                color: #FFF;
                line-height: 50px;
            }
            ul.list {
                font-size: 14px;
                margin-left: 20px;
                margin-right: 60px;
                color: #FFF;
                line-height: 50px;
                li {
                    margin-left: 10px;
                    a {
                        &:visited {
                            color: #FFF;
                        }
                        &:hover {
                            color: red;
                        }
                        &:active {
                            color: red;
                        }
                    }
                }
            }
        }
        .swiper-container {
            width: 100%;
            height: 250px;
            .swiper-wrapper {
                width: 100%;
                height: 100%;
                .swiper-slide {
                    background-position: center;
                    background-size: 100% 100%;
                    width: 100%;
                    height: 100%;
                    img {
                        width: 100%;
                        height: 100%;
                    }
                }
            }
            .swiper-pagination-bullet {
                width: 10px;
                height: 10px;
                display: inline-block;
                background: #7c5e53;
            }
        }
        .carousel-container {
            overflow: hidden;
            position: relative;
            width: 100%;
            height: 100px;
            .swiper-wrapper {
                overflow: hidden;
                width: 100%;
                height: 100%;
                .swiper-slide {
                    background-position: center;
                    background-size: 100% 100%;
                    img {
                        width: 100%;
                        height: 100%;
                    }
                }
            }

        }
        .scale-wrapper {
            display: inline-block;
                .slot {
                    height: 100%;
                    transition: .1s transform;
                    transform: translateZ(0);
                    /* hack */
                    img {
                        height: 100%;
                    }
                    &:hover {
                        z-index: 1;
                        img {
                            height: 100%;
                            transform: scale(1.1, 1.1);
                            transition: .3s transform;
                            box-shadow: 0 0 2px 1px rgba(0, 0, 0, 0.5);
                        }
                    }
                }
        }
    }
</style>
