<template>
	<view class="swiperbox">
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular autoplay=true interval="3000" duration="500">
				<swiper-item v-for="item in bannerList">
					<view>
						<image :src="item.image_src" mode="aspectFit"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		name: "swiper",
		props:['bannerList'],
		data() {
			return {
				
			};
		},
		mounted() {
			console.log(this.bannerList);
		}
		
	}
</script>

<style>
	.swiperbox{
		width: 100%
	}
	image{
		width: 100%;
		
	}
</style>