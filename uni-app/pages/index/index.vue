<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<!-- #ifdef H5-->
		<view>
			我只在H5里
		</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN-->
		<view>
			我只在小程序里
		</view>
		<!-- #endif -->
		<navigator url="../message/message" open-type="switchTab">我要去List</navigator>
		<button type="primary" @click="navigatorTo">导航跳转</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad(options) {
			console.log("页面加载了", options);
		},
		methods: {
			
			navigatorTo() {
				uni.navigateTo({
					url: '/pages/List/List'
				})
			}
		},

		// #ifdef H5
		// #endif
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>