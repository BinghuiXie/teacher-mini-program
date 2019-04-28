<template>
  <div class="scroll-news">
    <span class="news-info">青橙头条 | </span>
    <swiper
      vertical
      autoplay
      circular
      class="scroll-swiper"
    >
      <block
        v-for="(item, index) in scrollNewsData"
        :key="index"
      >
        <swiper-item>
          <span class="news-content">{{item}}</span>
        </swiper-item>
      </block>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: "scrollNews",
    data () {
      return {
        scrollNewsData: [
          "特朗普总统签订中美贸易协定计划",
          "希拉里总统签订中美贸易协定计划",
          "奥巴马总统签订中美贸易协定计划",
          "克林顿总统签订中美贸易协定计划",
          "小布什总统签订中美贸易协定计划"
        ]
      }
    }
  }
</script>

<style scoped lang="less">
  .scroll-news{
    height: 98rpx;
    background: rgba(255, 255, 255, 1);
    box-shadow: 0 1px 5px 0 rgba(218, 218, 218, 1);
    border-radius: 15px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    padding: 0 24rpx;
    display: flex;
    align-items: center;
    margin-bottom: 29rpx;
    .news-info{
      font-size: 32rpx;
      font-family: PingFangSC-Regular;
      color: rgba(62,201,88,1);
    }
    .scroll-swiper{
      width: 100%;
      height: 98rpx;
      border-left: 10rpx solid transparent;
      .news-content{
        font-size: 28rpx;
        font-family: PingFangSC-Regular;
        font-weight: 400;
        color: rgba(130,130,130,1);
        line-height: 98rpx;
      }
    }
  }
</style>
