<template>
  <div class="recommend-source">
    <header class="recommend-header">
      <span class="title">推荐生源</span>
      <span class="switch" @click="handleSwitchClick"><img :style="{rotate: rotateAngle + 'deg'}" src="http://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/spin.png">换一批</span>
    </header>
    <main class="recommend-main">
      <ul class="recommend-ul">
        <li
          class="recommend-item"
          v-for="(item, index) in recommendShowList"
          :key="index"
        >
          <img :src="item.imgURL" alt="">
        </li>
      </ul>
    </main>
  </div>
</template>

<script>
  export default {
    name: "recommendSource",
    data () {
      return {
        rotateAngle: 0,
        currentPage: 1,
        recommendList: [
          {
            "id": 0,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren1%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 1,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren2%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 2,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren3%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 3,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren3%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 4,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren1%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 5,
            "imgURL": "https://teacher-mini-program.oss-cn-beijing.aliyuncs.com/images/mainPage/ren2%402x.png",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 6,
            "imgURL": "http://n.sinaimg.cn/sinacn10111/416/w543h673/20190104/b928-hqzxptp4792978.jpg",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 7,
            "imgURL": "http://i.shangc.net/article/20190114/94e666609ffb0263c5e69db8d5282082.jpg",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          },
          {
            "id": 8,
            "imgURL": "https://pbs.twimg.com/media/DxeqywDXgAAR9P0.jpg",
            "name": "kris wu",
            "course": "数学",
            "level": "初二"
          }
        ],
        recommendShowList: []
      }
    },
    methods: {
      handleSwitchClick () {
        this.rotateAngle += 360;
        if (this.currentPage !== Math.ceil(this.recommendList.length / 3)) {
          this.currentPage += 1;
        } else {
          this.currentPage = 1;
        }
      }
    },
    computed: {
      set: function () {
        this.recommendShowList.splice(0, this.recommendShowList.length)
        for (let i = (this.currentPage - 1) * 3; i < this.currentPage * 3; i++) {
          this.recommendShowList.push(this.recommendList[i])
        }
      }
    }
  }
</script>

<style scoped lang="less">
  .recommend-source{
    margin-bottom: 30rpx;
    .recommend-header{
      display: flex;
      justify-content: space-between;
      line-height: 40rpx;
      font-size: 40rpx;
      margin-bottom: 30rpx;
      .switch{
        font-size: 34rpx;
        display: inline-block;
        height: 40rpx;
        img{
          width: 40rpx;
          height: 40rpx;
          vertical-align: -10rpx;
          transition: all .5s ease-in-out;
        }
      }
    }
    .recommend-main{
      .recommend-ul{
        display: flex;
        justify-content: space-between;
        .recommend-item{
          width: 224rpx;
          height: 258rpx;
          overflow: hidden;
          img{
            max-width: 100%;
            max-height: 100%;
          }
        }
      }
    }
  }
</style>
