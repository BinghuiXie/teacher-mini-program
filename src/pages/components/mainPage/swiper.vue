<template>
  <div class="swiper-box">
    <swiper
      autoplay
      circular
      class="swiperBox"
    >
      <block
        v-for="(item, index) in urlList"
        :key="index"
      >
        <swiper-item
          class="swiper-item"
        >
          <div class="imgBox">
            <img class="swiper-image" :src="item" alt="">
          </div>
        </swiper-item>
      </block>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: "SwiperComponent",
    data () {
      return {
        urlList: [
          "http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner%402x.png",
          "http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner%402x.png",
          "http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner%402x.png",
          "http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner%402x.png",
          "http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner%402x.png",
        ]
      }
    }
  }
</script>

<style scoped lang="less">
  .swiperBox{
    height: 350rpx;
    .swiper-item{
      width: 100%;
      box-sizing: border-box;
      padding: 29rpx 29rpx 0 29rpx;
      .imgBox{
        height: 100%;
        .swiper-image{
          width: 100%;
          height: 100%;
        }
      }
    }
  }
</style>
