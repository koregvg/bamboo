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
    </section>
</template>

<script>
    import headerBar from './header-bar/header-bar.vue'

    export default {
        name: 'index',
        data () {
            return {
                msg: 'Welcome to Your Vue.js App'
            }
        },
        components: {
            headerBar
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
    .page-index {
        .header-bar {
            position: fixed;
            .left-content {
                font-size:16px;
                margin-left: 30px;
                color: #FFF;
                line-height: 50px;
            }
            ul.list {
                font-size:14px;
                margin-left: 20px;
                margin-right: 60px;
                color: #FFF;
                line-height: 50px;
                li{
                    margin-left: 10px;
                    a{
                        &:visited{
                            color:#FFF;
                        }
                        &:hover{
                            color:red;
                        }
                        &:active{
                            color:red;
                        }
                    }
                }
            }
        }
    }
</style>
