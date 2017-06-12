<template>
    <nav class="header-bar">
        <div class="content" :style="{height: realHeight, backgroundColor: bgColor}">
            <div class="left-content">
                <slot name="left-content">左侧内容</slot>
            </div>
            <ul class="list">
                <li class="list-item" v-for="item in listItem">
                    <a :href="item.href">{{item.text}}</a>
                </li>
            </ul>
        </div>
    </nav>
</template>
<style lang="less" scoped>
    .header-bar {
        width: 100%;
        .left-content {
            margin-left: 30px;
            line-height: 50px;
            height: 100%;
            float: left;
        }
        ul.list{
            margin-left: 20px;
            line-height: 50px;
            height: 100%;
            float:right;
            li{
                margin-left: 10px;
                list-style: none;
                float:left;
            }
        }
    }
</style>
<script>
    const REM = 37.5;

    export default{
        props: {
            height: { // 项目ID
                type: Number,
                required: false,
                default: 50
            },
            bgColor: { // 项目ID
                type: String,
                required: false,
                default: 'rgba(40,204,131,1)'
            },
            listItem: {
                type: Array,
                required: true,
                default: [
                    {
                        text: '首页',
                        value: 0,
                    },
                    {
                        text: '帮助中心',
                        value: 1,
                    },
                    {
                        text: '联系我们',
                        value: 2,
                    },
                ]
            }
        },
        data(){
            return {
                msg: 'hello vue'
            }
        },
        computed: {
            realHeight(){
                return this.px2rem(this.height);
            }
        },
        components: {},
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
