<template>
  <div id="app">
    <!--    <div id="nav">-->
    <!--      <router-link to="/">Home</router-link> |-->
    <!--      <router-link to="/about">About</router-link>-->
    <!--    </div>-->

    <!-- 结合router，缓存部分页面 -->
    <keep-alive>
      <router-view v-if="$route.meta.keepAlive"></router-view>
    </keep-alive>
    <router-view v-if="!$route.meta.keepAlive"></router-view>
    <div>修改APP 测试git合并问题</div>
  </div>
</template>-

<script>

export default {
  methods: {
    p(top, right, bottom, left) {
      return {
        // 上右下左
        padding:
          top +
          "px" +
          " " +
          right +
          "px" +
          " " +
          bottom +
          "px" +
          " " +
          left +
          "px"
      };
    },
    m(top, right, bottom, left) {
      return {
        // 上右下左
        margin:
          top +
          "px" +
          " " +
          right +
          "px" +
          " " +
          bottom +
          "px" +
          " " +
          left +
          "px"
      };
    },

    // 字体大小、颜色、是否加粗,行高(即行间距,和字体相同大小时,行间距为0)、字体类型
    // 除了size之后的4个不设置时,可以填0
    f(size, color, isBold, lineheight, family) {
      var vf = {
        // 上右下左
        "font-size": size + "px"
      };
      if (color != 0) {
        vf["color"] = color;
      }
      if (isBold != 0) {
        vf["font-weight"] = "bold";
      }
      if (lineheight != 0) {
        vf["line-height"] = lineheight + "px";
      }
      if (family != 0) {
        vf["font-family"] = family;
      }

      return vf;
    }
  }
};
</script>

/*
  ➤如果想设置一些全局的样式, 可以在App.vue文件中的style标签中添加,因为App.vue中的style标签没有添加scoped;
  ➤如果不添加scoped, 会把当前的style标签中的样式设为全局样式,各当个vue文件容易混淆不知道哪个是当前的样式,所以推荐必须要加上
  ➤也可以创建一个xx.css文件,写好样式,然后main.js中引入也是全局的样式.
*/
<style lang="less">
p {
  margin: 0px;
  padding: 0px;
}
</style>
