<template>
  <div>
    <top-navigation />
    <div class="main-content">
      <main-swiper />
      <div class="content-box">
        <main-scroll></main-scroll>
        <div class="main-funcs">
          <div class="funcs-item" v-for="(item, index) in funcList">
            <div class="imgBox">
              <img :src="item.iconURL" alt="">
            </div>
            <span class="func-name">{{item.funcName}}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import TopNavigation from '../../commonComponents/topNavigation'
  import MainSwiper from '../components/mainPage/swiper'
  import MainScroll from '../components/mainPage/scrollNews'
  export default {
    name: "mainPage",
    data () {
      return {
        funcList: [
          {
            "iconURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/kecheng%402x.png",
            "funcName": "发布课程"
          },
          {
            "iconURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/dingdan%402x.png",
            "funcName": "订单管理"
          },
          {
            "iconURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/xuesheng%402x.png",
            "funcName": "我的学生"
          },
          {
            "iconURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/pipei%20%402x.png",
            "funcName": "匹配学生"
          }
        ]
      }
    },
    components: {
      TopNavigation,
      MainSwiper,
      MainScroll
    }
  }
</script>

<style scoped lang="less">
  .content-box{
    border: 29rpx solid transparent;
    border-top: 29rpx solid transparent;
    .main-funcs{
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      .funcs-item{
        width: 316rpx;
        height: 316rpx;
        border-radius: 30rpx;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        background-color: #2eb268;
        margin-right: 20rpx;
        margin-bottom: 20rpx;
        &:nth-of-type(even){
          margin-right: 0;
        }
        &:nth-of-type(1){
          background: linear-gradient(135deg, rgba(102, 208, 255, 1), rgba(83, 160, 255, 1));
        }
        &:nth-of-type(2){
          background: linear-gradient(135deg, rgba(255, 223, 89, 1), rgba(255, 172, 82, 1));
        }
        &:nth-of-type(3){
          background: linear-gradient(135deg, rgba(255, 180, 139, 1), rgba(255, 87, 82, 1));
          .imgBox{
            width: 118rpx;
            height: 100rpx;
          }
        }
        &:nth-of-type(4){
          background: linear-gradient(135deg, rgba(91, 228, 127, 1), rgba(68, 170, 140, 1));
          .imgBox{
            height: 100rpx;
          }
        }
        .imgBox{
          width: 106rpx;
          height: 114rpx;
          margin-bottom: 40rpx;
          img{
            width: 100%;
            height: 100%;
          }
        }
        .func-name{
          display: inline-block;
          width: 100%;
          text-align: center;
          color: #ffffff;
        }
      }
    }
  }
</style>
