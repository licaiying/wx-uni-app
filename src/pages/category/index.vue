<template>
  <view class="box">
    <search></search>
  </view>
  
</template>

<script type="text/javascript">
// 导入封装好的search组件
import search from '@/components/search.vue'

export default {
  data() {
    return {

    }
  },
  // 注册组件
  components: {
    search
  }
}
</script>

<style scoped lang="less" >
</style>
