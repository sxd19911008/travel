<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- 循环展示轮播图图片，注意一定要加key -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <!-- 传入src，需要加冒号 -->
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <!-- 轮播图下面的小点，要让展示的那一页显示白色 -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        // 添加该属性让轮播图小圆点显示出来
        pagination: '.swiper-pagination',
        // 是否循环展示
        loop: true
      },
      // 写一个轮播图数组，循环展示即可
      swiperList: [{
        id: '0001',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/700528b360c39d630dda13930a92a1a6.jpg_750x200_80f6150c.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/2f5f3ea4698c9b7898db7562d89b91ed.jpg_750x200_bd3b4ce9.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
// 穿透scoped设定，让样式可以继承到子组件指定class下。
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff !important
.wrapper
  // 解决图片加载完成前，无法父元素撑起高度的问题
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 26.66%
  // 让图片没显示出来时，有一个灰色背景
  background: #eee
  // 让宽度自适应屏幕
  .swiper-img
    width: 100%
</style>
