<template>
	<view>
		<swiperBox :bannerList='bannerList'></swiperBox>
	</view>
</template>

<script>
	import swiper from '../../components/swiper.vue'
	export default {
		data() {
			return {
				bannerList: []
			}
		},
		onLoad: function(option) {
			uni.request({
				url: "https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata",
				method: 'GET',
				success:res=> {
					console.log(res.data.message);
					this.bannerList=res.data.message
				}
			})
		},
		methods: {

		},
		components: {
			swiperBox: swiper
		}
	}
</script>

<style>

</style>