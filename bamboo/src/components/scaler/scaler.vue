<template>
    <div class="scale-wrapper" :style="{width:realWidth, height:realHeight}">
        <slot name="content">
            <div>
                <div :style="{backgroundColor:'blue'}"></div>
            </div>
        </slot>
    </div>
</template>

<script>
    const REM = 37.5;

    export default {
        props: {
            width: { // 项目ID
                type: Number,
                required: false,
                default: 100
            },
            height: { // 项目ID
                type: Number,
                required: false,
                default: 100
            },
        },
        computed: {
            realHeight(){
                return this.px2rem(this.height);
            },
            realWidth(){
                return this.px2rem(this.width);
            }
        },
        methods: {
            px2rem(value) {
                if (typeof value !== 'number' || isNaN(value)) {
                    return value;
                }

                return (value / REM + 0.0001).toFixed(4) + 'rem';
            }
        }
    }
</script>

<style lang="less" scoped>
    .scale-wrapper {
        display: inline-block;
        > div {
            height: 100%;
            transition: .1s transform;
            transform: translateZ(0);
            > div{
                height: 100%;
            }
            /* hack */
            &:hover {
                z-index: 1;
                > div {
                    transform: scale(1.1, 1.1);
                    transition: .3s transform;
                    box-shadow: 0 0 2px 1px rgba(0, 0, 0, 0.5);
                }
            }
        }
    }
</style>