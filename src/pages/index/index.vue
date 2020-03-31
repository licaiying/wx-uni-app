<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
		<!-- 演示：示例代码 -->
		<!-- 可以使用小程序的标签，但是语法可以是vue的语法 -->
		<view v-for="(item,index) in arr" :key="index">{{item}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello 小程序',
				arr:['a','b','c']
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
