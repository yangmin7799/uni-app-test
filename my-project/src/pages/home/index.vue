<template>
  <view class="home-page">
    <view class="search-content">
      <input type="text" placeholder="热门搜索">
    </view>
    <view>首页图片</view>
    <view class="hot-txt">
      <view v-for="hot in hotTxt" :key="hot.name" class="hot">{{hot.name}}</view>
    </view>
    <view>消息快讯列表</view>
  </view>
</template>

<script>
export default {
  data(){
    return {
      hotTxt: [
        {name: "地摊"},
        {name: "疫情"},
        {name: "明星"}
      ]
    }
  }
}
</script>

<style lang="scss">
  .home-page{
    .search-content{
      padding: 5px 10px;
      // background-color: #8abff5;
      .uni-input-placeholder {
        color: #ffff;
      }
      .uni-input-input{
        width: 70%;
        color: #ffff;
      }
    }
    .hot-txt{
      padding: 5px 10px;
      display: flex;
      justify-content: space-around;
      align-items: center;
      .hot{
        width: 55px;
        height: 55px;
        border-radius: 50%;
        line-height: 55px;
        background-color: rgba(68, 218, 205, 0.904);
        color: #fff;
        font-size: 12px;
      }
    }
  }
</style>