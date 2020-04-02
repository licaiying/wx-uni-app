<template>
  <view class="search" :class="{'focus':focus}">

    <!-- 搜索区域 ：默认先显示-->
    <view class="search_box">
      <!-- 搜索框 -->
      <input type="text" @focus="iptFocus"  :placeholder="placeholder" />

      <!-- 取消按钮 -->
      <view class="cancel" @click="iptCancel">取消</view>

      <!-- 图标 -->
      <view class="icon_1">搜索</view>
      <view class="icon_2"></view>

    </view>

    <!-- 历史搜索记录，默认先隐藏 -->
    <view class="history"></view>

  </view>
</template>

<script type="text/javascript">
export default {
  data() {
    return {
      // 默认，不添加类名
      focus:false,

      placeholder:""
    };
  },

  methods:{
    // 聚焦的时候，执行该函数
    iptFocus(){
      // 添加类名
      this.focus = true
      this.placeholder = "请输入您想要的商品"

      // 1 获取数据
      // 1.1 获取手机窗口高度？API  getSystemInfoSync 同步获取；
      // 1.2. 所有api:wx；uni-app：uni.
      var res = uni.getSystemInfoSync()
      // console.log(res)

      // 2.将获取的可用窗口的高度传递给父组件
      // 子-->父 传值  使用自定义事件
      // windowHeight:可用窗口的高度，API的参数，可参考getSystemInfoSync()
      this.$emit('send',res.windowHeight + "px")
    },

   // 点击 取消按钮 的时候，不添加类名
    iptCancel(){
      this.focus = false
      this.placeholder = ""

      // 当是 取消按钮 的状态时，即搜索框是默认状态时，将 auto 传递给父组件 使其保持其原有的高度
      this.$emit("send","auto")
    }
  }
};
</script>

<style scoped lang="less" >
// 搜索区域
// 默认状态
.search {
  box-sizing: border-box;
  padding: 20rpx 16rpx;
  background-color: #ff2d4a;

    .search_box {
      position: relative;
      input {
      height: 60rpx;
      width: 100%;
      background-color: #fff;
      border-radius: 8rpx;
    }

    .cancel {
      display: none;
    }

    // 图标1 显示 绝对定位
    .icon_1 {
      display: block;
      height: 32rpx;
      line-height: 32rpx;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%,-50%);
      font-size: 24rpx;
      color: #bbbbbb;
      background: url('http://static.botue.com/ugo/images/icon_search%402x.png') no-repeat;
      background-size: 32rpx;
      padding-left: 50rpx;
    }
    // 图标2 隐藏
    .icon_2 {
      display: none;
    }
  }

    // 历史搜索记录区域
    .history {
      display: none;
    }
}

// 聚焦状态
.focus {
  background-color: #ccc;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 999;

   .search_box {
     display: flex;
     position: relative;
      input {
      height: 60rpx;
      background-color: #fff;
      border-radius: 8rpx;
      flex: 1;
      padding-left: 70rpx;
      font-size: 24rpx;
    }

    .cancel {
      display: block;
      box-sizing: border-box;
      width: 160rpx;
      height: 60rpx;
      text-align: center;
      border: 1px solid #999;
      line-height: 60rpx;
      border-radius: 10rpx;
      font-size: 30rpx;
      margin-left: 30rpx;
    }

     // 图标1 隐藏
    .icon_1 {
      display: none;
    }
    // 图标2 显示
    .icon_2 {
      display: block;
      width: 32rpx;
      height: 32rpx;
      position: absolute;
      left: 20rpx;
      top: 50%;
      transform: translateY(-50%);
      background: url('http://static.botue.com/ugo/images/icon_search%402x.png') no-repeat;
      background-size: 32rpx;
    }
  }

  // 历史搜索记录区域
  .history {
    display: block;
    position: absolute;
    top: 100rpx;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ddd;
  }
}
</style>
