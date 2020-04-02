<template>
  <view class="search" :class="{'focus':focus}">

    <!-- 搜索区域 ：默认先显示-->
    <view class="search_box">
      <!-- 搜索框 -->
      <input type="text" @focus="iptFocus" />

      <!-- 取消按钮 -->
      <view class="cancel">取消</view>
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
      focus:false
    };
  },

  methods:{
    // 聚焦的时候，执行该函数
    iptFocus(){
      // 添加类名
      this.focus = true
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
      input {
      height: 60rpx;
      width: 100%;
      background-color: #fff;
      border-radius: 8rpx;
    }

    .cancel {
      display: none;
    }
  }
 
}

// 聚焦状态
.focus {
  background-color: #ccc;

   .search_box {
      input {
      height: 60rpx;
      width: 100%;
      background-color: #fff;
      border-radius: 8rpx;
    }

    .cancel {
      display: block;
    }
  }
}
</style>
