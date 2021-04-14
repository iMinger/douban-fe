
<!-- 组件说明 -->
<template>
    <div class='talion-view'>
        <div class="header-bar">
            <span class="close-talion" @click="closeTalion">关闭</span>
            <form class="search" onsubmit='return false'>
                <input type="search" name="query" v-model.trim.lazy='queryStr' @keyup.enter='goSearch()'>
            </form>
        </div> 
        <ul class="has-header">
            <li>
                <div>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(35, 132, 232);">电影</strong>
                        <span>影院热映</span>
                    </a>

                    <a href="#" target="_blank">
                        <strong style="color: rgb(230, 70, 126);">同城</strong>
                        <span>周末活动</span>
                    </a>

                    <a href="#" target="_blank">
                        <strong style="color: rgb( 159, 120, 96);">阅读</strong>
                        <span>电子书</span>
                    </a>

                    <a href="#" target="_blank">
                        <strong style="color: rgb(35, 132, 232);">东西</strong>
                        <span>心爱之物</span>
                    </a>
                </div>
            </li>

            <li>
                <div>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(122, 106, 219);">电视</strong>
                         <span>正在热播</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb( 42, 184, 204);">小组</strong>
                         <span>志趣相投</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(87, 116, 197);">游戏</strong>
                         <span>虚拟世界</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(64, 207, 169);">FM</strong>
                         <span>红心歌单</span>
                    </a>
                </div>
            </li>

            <li>
                <div>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(159, 120, 96);">图书</strong>
                        <span>畅销排行</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(244, 143, 46);">音乐</strong>
                        <span>新碟榜</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(89, 108, 221);">应用</strong>
                        <span>玩手机</span>
                    </a>
                    <a href="#" target="_blank">
                        <strong style="color: rgb(66, 189, 86);">市集</strong>
                        <span>购买原创</span>
                    </a>
                </div>
            </li>
        </ul>   
    
    </div>
</template>

<script>

    //这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
    //例如：import 《组件名称》 from '《组件路径》';
    export default {
        name:'TalionView',
        components: {
            
        },
        data () {
            //这里存放数据
            return {
                queryStr: ''
            };
        },
        //监听属性 类似于data概念
        computed: {

        },
        //方法集合
        methods: {
            closeTalion() {
                this.$emit('closeTalion');
            },

            goSearch() {
                this.$emit('closeTalion');
                // 跳转到搜索页面
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

<style>

.talion-view {
    /*相对窗口位置固定，一般可以用导航栏等组件*/ 
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: #fff;
    /*设置 css 层叠样式优先性*/ 
    z-index: 999;
}

.close-talion {
    color: #42bd56;
    font-size: 1.6rem;
}

.search {
    flex: 1;
    width: 100%;
    padding-left: 1rem;
}

input[type=search] {
    box-sizing: border-box;
    /*边的宽度为 0*/ 
    border: 0;
    background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADQAAAA0CAYAAADFeBvrAAAABGdBTUEAALGPC/xhBQAABUlJREFUaAXdWT1oHEcU1unHR8ih0lZEKsWVkSrLkFaVQIYkJ93JBBUp0hm7sdMJbOlAnR0ICDdJk4AL6++wi8PChXAXMG6CMSmSTpZlFy7EmWBLQvm+5c3ydrTam9nblXQeWM2bN/N+vntvZ2afuro+sVZoB0+9Xv9qd3f3W+i4WCgUBg8ODgZB82HbAm8LvC3Qz/v6+h6Wy+V/g5kc/3gDWltbO7u/v38Njpbh17Cnby8Ast7T07M4OTn51lPWabkzoKWlpRKcuQkgP0FzyUn70Yua0HUHuu5OT083j17mP+MEaHl5eRLG70H9OX8TiRJvAOxqtVpdS1zlMZkICCAKKysrt6DvNukYvR/B24BTj9C/RCpt7e3t8Z3p6u3tHURq8n26ANlv0I/hOYMn0iB7AMZ8pVKpCR2Z9x3EORnoQIp9BuIPPJUYpdvg1Uql0v2JiYmdmPlDrEaj0d9sNmcwwR9owF4AMMsA/gNS8D97zmccC4jRQJotQVEEDIx+AG+hv7//5/Hx8fc+hsza9fX1z3d2dm5gPAs7RcNnT1CI1JV2IhULCGBuw9icNgZ6GylVnpqa+tPipxqurq5+jZSsQzgSLYCZwzs1n0ophA4B4gYA/gqjZJTCyF/d3d2XAWbT8LLoAepLgGpA14jRJ9GppN0oQqepkFszun/w6N2MkbmUNRjaYxNQz0DqSL3B+HyaLb2bSk3Dr3MTdAgG4w+SZplGxthjzx+KNmhL8c+JL4rlRoaAeANAmvHQ1G0hq3dGK7VpsbGg+fSFPmmeCx0CQi5fh4C+AWxzN3NRksUascXjwLQSfLpmBq59CAi/yHeWUC3t1mzpcRqKrZpeDJ94X/RqASDemiE1rCQ/8tBU42MhxSZvH6YNi29m3LIPAMkngF684XoD0ELt0mJzQ+uJ8U1PH6JNyl3UM9hheDc7kRZjO+JbK6cCQFBiPsrM+peGOIE+YjvGt0SXAkB4+SKAcC4EN+ZEyZwmbdu2b63MmpSLADKfAK2E85iPsR3xrZVNk3L8JglbsViMXInCiWMgYmx7+WJS7rX2FQfaF3p8nHSMba/ag4lQ5J2BUq8wZwk4xjYvqs7NRCgCCNIXnDVkv9C2/crHRAAIAs+1EHYW1gBOpNm2sW0/9XEkAMQioCU0xhqAxct9KDbHtCEAeqLHregAkFQ0X6jFZ6SgoVj5k2IzrAwBzCZqDH/7WDYpxwIFv+91u8WChmbkSYstVoTChvT7NRw4EiEgnNCLkGkquQGpzihWfqTY0p/hrCrRJ68WAmKtGVG6Y0nPsjpj8TIfio1ZS/FvqCm8s3gthyEgrkSI76IL932MizgX6ixktNSUcoEUSeq0pVTwGKmpsTMZAcQqC6J0FY++Cg0AVCMPUAKGZSydanT+xzTRoWAEEBlSD5snrdoIQD2DA5mlH3VRJ2yENTmx9whgHivbXmTsxQ/hZ5H+Afqq1obI5VoKFlv76GcA6oG27UrHAqIwi/UA8LsNShRnXqy3HE4N6khANCCRyvXfKQKEn/yX8fTImF0qUImAjPIc/+HF3YwbwGNkxBXQrDS1BerQpmBA6F42ivNIwTnw9eGrl/nQPDR/wTNiNgB5Z2bAY2RMI7j7AtbwEnunCGkN7fzTGD/IJtKY15lFAIg9NNuNlDcgDS7h3/rUyy9NHtKvAOQpnieuF812QLUFSIPLmk4L6tQC4g+UBtSpBpQG1KkH5AuqIwD5gOoYQK6gOgqQCyinmwIVnZaWcKMIvgw6DhB/WBsUDu2HQ0ND33Ou41KOTpsm51SVYEZHR3cN/5Pq/wfEdlFyq1lD2AAAAABJRU5ErkJggg==) no-repeat 50% #f3f3f3;
    background-size: 1.73rem;
    /*设置边框的圆角*/ 
    border-radius: 0.3rem;
    /*宽占满父组件*/ 
    width: 100%;
    /*高固定为 3.2rem*/ 
    height: 3.2rem;
    font-size: 1.4rem;
}

/*设置 input[type=search] 的 focus 伪类*/ 
input[type=search]:focus {
    background: #f3f3f3;
}

ul {
    /*设置为弹性盒子布局*/ 
    display: flex;
    /*沿着弹性容器当前线的主轴对齐弹性项目元素*/ 
    justify-content: space-between;
    padding-top: 2.5rem;  
    
}

ul li {
     width: 33.33%;
     box-sizing: border-box;
}

ul div {
    /* relative  他的意思是绝对相对定位，他是参照父级的原始点为原始点，
    无父级则以BODY的原始点为原始点，配合TRBL进行定位，
    当父级内有padding等CSS属性时，当前级的原始点则参照父级内容区的原始点进行定位
    */ 
    position: relative;
    /*左浮动*/ 
    float: left;
    top: 0;
}

ul a{
    position: relative;
    top: 0;
    display: block;
    margin: 2.5rem auto;
    text-align: center;
}



ul strong {
    display: block;
    font-weight: 400;
    font-size: 2.4rem;
    line-height: 2.8rem;
}

ul  span {
    /*块级元素，会单独占一行*/ 
    display: block;
    color: #999;
    height: 1.7rem;
    font-size: 1.2rem;
    letter-spacing: 0.1rem;
}

</style>