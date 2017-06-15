<template>
    <div class="box-gallery-wrapper" :class="{'hasShadow':needShadow}" :style="{width:realWidth, height:realHeight}">
        <slot name="content">
            <div>
                <div class="inner-box" :style="{width:realInnerWidth, height:realInnerHeight}">
                    <div class="inner-content">Hello</div>
                </div>
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
            innerWidth: {
                type: Number,
                required: false,
                default: 50
            },
            innerHeight: {
                type: Number,
                required: false,
                default: 50
            },
            needShadow: {
                type: Boolean,
                required: false,
                default: true
            }
        },
        computed: {
            realHeight(){
                return this.px2rem(this.height);
            },
            realWidth(){
                return this.px2rem(this.width);
            },
            realInnerHeight(){
                return this.px2rem(this.innerHeight);
            },
            realInnerWidth(){
                return this.px2rem(this.innerWidth);
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
    .box-gallery-wrapper {
        position: relative;
        margin-left: 50px;
        display: inline-block;
        background-color: blue;
        > div {
            height: 100%;
            background: url('./img/example.jpeg') no-repeat;
            background-size: 100% 100%;
            .inner-box {
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background-color: rgba(255, 255, 255, 0.5);
                display: none;
            }
        }
        &:hover {
            > div {
                .inner-box {
                    display: block;
                }
            }
            &.hasShadow {
                box-shadow: 0 0 2px 1px rgba(0, 0, 0, 0.5);
            }
        }
    }
</style>