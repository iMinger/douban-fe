<template>
  <div id="app">
    <router-view class="view"></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

/* base setting and rest */
html {
  /* 这样设置的好处是 16*62.5% = 10  1rem = 10px， 那么这样以后计算器 rem 和 px 之间的关系就会比较方便 */
  font-size: 62.5%; 
}

#app {
  /* max-width: 41.2rem; */
  /* 上下外边距 0px, 左右水平居中 */
  margin: 0 auto;
}

.has-header {
  margin-top: 4.8rem;
}

h2 {
  font-size: 1.68rem;
  font-weight: normal;
  color: #111;
}

ul,li,a,h2 {
  margin: 0;
  padding: 0;
}

/* 取消 li 的 左侧的圆点*/
li {
  list-style: none;
}

a {
  /* 取消 a 元素的链接的下划线 */
  text-decoration: none;
}

.header-bar {
  /* fixed ： 元素的位置相对于浏览器窗口是固定位置。即使窗口是滚动的它也不会移动.一般用于导航栏等固定位置的元素 */
  position: fixed;
  left: 0;
  right: 0;
  top: 0;

  /* 设置层叠展示的优先级，数字越大，优先级越高，距离人眼越近 */
  z-index: 998;
  /* 一般 display: 后面有 inline, block , inline-block, hidden 等 */
  display: flex;
  /* align-item 属性将所有直接子节点上的 align-self 值设置为一个组。align-self 属性设置项目在其包含块中在交叉轴方向上的对齐方式
  具体效果可查看：https://developer.mozilla.org/zh-CN/docs/Web/CSS/align-items
   */
  align-items: center;
  height: 4.8rem;
  padding: 0 1.8rem;
  background: #fff;
  /* 底部的 border： 1 像素宽， solid: 实线 颜色 #f3f3f3 */
  border-bottom: 0.1rem  solid #f3f3f3;
}


</style>
