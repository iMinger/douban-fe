<!-- 组件说明 -->
<template>
    <div class='pages-view'>
        <header-bar @showTalion='open'></header-bar>
        <router-view></router-view>
        <talion-view v-show="talion" @closeTalion='close'></talion-view>
    </div>
</template>

<script>
    //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
    //例如：import 《组件名称》 from '《组件路径》';
    import HeaderBar from '../components/HeaderBar'
    import TalionView from '../components/TalionView'
    export default {
        name: 'pages-view',
        components: {
            HeaderBar, TalionView
        },
        data () {
            //这里存放数据
            return {
                talion:'',
            };
        },
        //监听属性 类似于data概念
        computed: {

        },
        //方法集合
        methods: {
            open(){
                this.talion = 'open'
            },

            close(){
                this.talion = ''
            }
        },
        //生命周期 - 挂载完成（可以访问DOM元素）
        mounted() {

        },
        beforeCreate() {}, //生命周期 - 创建之前
        beforeMount() {}, //生命周期 - 挂载之前
        beforeUpdate() {}, //生命周期 - 更新之前
        updated() {}, //生命周期 - 更新之后
        beforeDestroy() {}, //生命周期 - 销毁之前
        destroyed() {}, //生命周期 - 销毁完成
        activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
    }
</script>

<style  scoped>

</style>