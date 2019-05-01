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
        <!--教学计划-->
        <div class="edu-plan">
          <span class="title">教学计划</span>
          <div class="edu-plan-block">
            <span class="add-plan-hint">你还没有添加教学计划哦~</span>
            <div class="add-plan-button">
              <span>添加教学计划</span>
            </div>
          </div>
        </div>
        <!--推荐生源-->
        <main-recommend></main-recommend>
        <!--适合我的-->
        <div class="fit-me">
          <div class="title"><span>适合我的</span></div>
          <div class="discribe"><span>填写或完善想授课的课程类型，并打开提醒器，我们会给你推送合适的订单哦～</span></div>
          <div class="fill-button"><span>去填写</span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import TopNavigation from '../../commonComponents/topNavigation'
  import MainSwiper from '../components/mainPage/swiper'
  import MainScroll from '../components/mainPage/scrollNews'
  import MainRecommend from '../components/mainPage/recommendSource'
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
      MainScroll,
      MainRecommend
    }
  }
</script>

<style scoped lang="less">
  .main-content{
    padding-top: 172rpx;
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
      .edu-plan{
        margin-bottom: 30rpx;
        .title{
          display: inline-block;
          font-size: 40rpx;
          line-height: 1.2;
          border-bottom: 10rpx solid transparent;
        }
        .edu-plan-block{
          height: 220rpx;
          border-radius: 48rpx;
          background: url("http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner1%402x.png") center center no-repeat;
          background-size: 100% 100%;
          padding: 36rpx 0;
          display: flex;
          justify-content: center;
          flex-wrap: wrap;
          .add-plan-hint{
            color: #ffffff;
            font-size: 30rpx;
            font-family: PingFangSC-Regular;
            margin-bottom: 60rpx;
            display: inline-block;
            width: 100%;
            text-align: center;
          }
          .add-plan-button{
            width: 250rpx;
            border-radius: 60rpx;
            border: 3rpx solid rgba(91, 228, 127, 1);
            color: rgba(91, 228, 127, 1);
            display: flex;
            align-items: center;
            span{
              font-size: 28rpx;
              text-align: center;
              display: inline-block;
              width: 100%;
              line-height: 1;
            }
          }
        }
      }
      .fit-me{
        background: url(https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/banner2%402x.png) center center no-repeat;
        background-size: 100% 100%;
        padding: 20rpx 20rpx 20rpx 28rpx;
        padding-left: 28rpx;
        box-sizing: border-box;
        border-radius: 48rpx;
        .title{
          span{
            font-size: 28rpx;
            font-family: PingFangSC-Regular;
            color: rgba(255,255,255,1);
            line-height: 1.5;
          }
        }
        .discribe{
          span{
            font-size: 24rpx;
            font-family: PingFangSC-Regular;
            color: rgba(255,255,255,1);
            opacity: 0.5;
            line-height: 0;
          }
        }
        .fill-button{
          margin: 0 auto;
          border-radius: 30rpx;
          width: 250rpx;
          border-radius: 60rpx;
          border: 3rpx solid rgba(91, 228, 127, 1);
          color: rgba(91, 228, 127, 1);
          font-size: 28rpx;
          text-align: center;
          line-height: 2;
          margin-bottom: 20rpx;
        }
      }
    }
  }
</style>
