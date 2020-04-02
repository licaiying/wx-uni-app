<template>
	<view class="content" :style="{'height':height,'overflow':'hidden'}">

		<!-- 搜索区域 -->
		<!-- 使用封装好的search组件 -->
		<search @send="send"></search>

		<!-- 轮播图区域 -->
		<swiper class="swiper">
			<swiper-item>
				<navigator url="">
                  <image src="/static/uploads/banner1.png"></image>
				</navigator>
			</swiper-item>
			<swiper-item>
				<navigator url="">
                  <image src="/static/uploads/banner2.png"></image>
				</navigator>
			</swiper-item>
			<swiper-item>
				<navigator url="">
                  <image src="/static/uploads/banner3.png"></image>
				</navigator>
			</swiper-item>
		</swiper>

		<!-- 导航区域 -->
		<view class="nav">
			<navigator url="">
				<image src="/static/uploads/icon_index_nav_1@2x.png"></image>
			</navigator>
			<navigator url="">
				<image src="/static/uploads/icon_index_nav_2@2x.png"></image>
			</navigator>
			<navigator url="">
				<image src="/static/uploads/icon_index_nav_3@2x.png"></image>
			</navigator>
			<navigator url="">
				<image src="/static/uploads/icon_index_nav_4@2x.png"></image>
			</navigator>
		</view>

		<!-- 楼层区域 -->
		<view class="floors">

		  <!-- 公共楼层:第一层 -->
		  <view class="item first">
			  <!-- 标题 -->
			  <view class="title">
				  <image src="/static/uploads/pic_floor01_title.png"></image>
			  </view>
			  <!-- 图片区域 -->
			  <view class="imgs">
				  <navigator url="">
					  <image src="/static/uploads/pic_floor01_1@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor01_2@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor01_3@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor01_4@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor01_5@2x.png"></image>
				  </navigator>
			  </view>
		  </view>
          
		  <!-- 公共楼层:第二层 -->
		  <view class="item">
			  <!-- 标题 -->
			  <view class="title">
				  <image src="/static/uploads/pic_floor02_title.png"></image>
			  </view>
			  <!-- 图片区域 -->
			  <view class="imgs">
				  <navigator url="">
					  <image src="/static/uploads/pic_floor02_1@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor02_2@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor02_3@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor02_4@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor02_5@2x.png"></image>
				  </navigator>
			  </view>
		  </view>

		   <!-- 公共楼层:第三层 -->
		  <view class="item">
			  <!-- 标题 -->
			  <view class="title">
				  <image src="/static/uploads/pic_floor03_title.png"></image>
			  </view>
			  <!-- 图片区域 -->
			  <view class="imgs">
				  <navigator url="">
					  <image src="/static/uploads/pic_floor03_1@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor03_2@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor03_3@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor03_4@2x.png"></image>
				  </navigator>
				  <navigator url="">
					  <image src="/static/uploads/pic_floor03_5@2x.png"></image>
				  </navigator>
			  </view>
		  </view>

		</view>
	
	</view>
</template>

<script>
// 导入封装好的search组件
import search from '@/components/search.vue'

	export default {
		data() {
			return {
				// 父组件(首页)的高度默认值，不需要设置高度，自动的
				height:'auto'
			}
		},
		
    // 注册search组件
		components:{
			search
		},

		methods:{
			send(e){
			//   console.log(e)
			this.height = e
			}
		}
	}
</script>

<style lang="less">
	.content {

		// 轮播图区域
		.swiper {
			height: 340rpx;
			image {
				width: 750rpx;
				height: 340rpx;
			}
		}

		// 导航区域
		.nav {
			display: flex;
			navigator {
				flex: 1;
				display: flex;
				flex-direction: column;
				align-items: center;
				image {
					margin: 24rpx 0 29rpx;
					width: 128rpx;
					height: 140rpx;
				}
			}
		}

		// 楼层区域
		.floors {
			.item {
				.title {
					box-sizing: border-box;
					padding-top: 20rpx;
					padding-left: 16rpx;
					background-color: #f6f3f6;
					image {
						width: 100%;
						height: 60rpx;
					}
				} 

				.imgs {
					box-sizing: border-box;
					padding: 20rpx 12rpx;
					overflow: hidden;
					navigator {
						float: left;
						margin-right: 10rpx;
						image {
							width: 100%;
							height: 100%;
						}
					}
					// 1
					navigator:nth-child(1) {
						width: 232rpx;
						height: 386rpx;  
					}
					// 2 5
					navigator:nth-child(2),
					navigator:nth-child(5) {
						width: 273rpx;
						height: 188rpx;
					}
					// 3 4 
					navigator:nth-child(3),
					navigator:nth-child(4) {
						width: 203rpx;
						height: 188rpx;
					}
					// 3 5 没有 margin right
					navigator:nth-child(3),
					navigator:nth-child(5) {
						margin-right: 0;
					}
					// 2 4 设置 margin bottom
					navigator:nth-child(2),
					navigator:nth-child(4) {
						margin-bottom: 10rpx;
					}
				}
			}

       // 第一楼层
			.first {
				.imgs {
					// 2 3 4 5 图片改变宽 高
					// n:从0开始，n放在前面，放在后面虽然不会报错，但是没有效果
					navigator:nth-child(n+2) {
					  width: 236rpx;
					  height: 188rpx;
				}
			}
		}
   }

}
	
</style>