<template>
  <div class="top-nav"></div>
</template>

<script>
  export default {
    name: 'topNavigation'
  }
</script>

<style scoped lang="less">
  .top-nav{
    position: fixed;
    top: 0;
    left: 0;
    width: 750rpx;
    height: 172rpx;
    background:linear-gradient(180deg,rgba(91,242,61,1),rgba(46,178,104,1));
    z-index: 100;
  }
</style>
