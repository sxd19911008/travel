<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      城市
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

// 引用stylus。scoped：这些样式只对本组件有效
<style lang="stylus" scoped>
// 引入自定义的styl文件，style样式中，使用路径别名，需要加一个~
@import '~styles/varibles.styl'
// stylus语法，不用大括号
.header
  // flex布局
  display: flex
  // 行高
  line-height: .86rem
  background: $bgColor
  color: #fff
  .header-left
    width: .64rem
    float: left
    .back-icon
      text-align: center
      font-size: .4rem
  .header-input
    flex: 1
    // 不能删除高度样式，否则input框不居中
    height: .64rem
    // 由于文字无法上下居中，添加行高样式
    line-height: .64rem
    margin-top: .12rem
    margin-left: .2rem
    padding-left: .2rem
    background: #fff
    border-radius: .1rem
    color: #ccc
  .header-right
    width: 1.24rem
    float: right
    text-align: center
    .arrow-icon
      margin-left: -.04rem
      font-size: .24rem
</style>
