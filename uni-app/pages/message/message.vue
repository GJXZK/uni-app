<template>
	<view>
		HEllO-uni<br/>
		<text selectable>谢资康下啊啊222</text>
		<button type="primary" @click="clickHandle(20,$event)">按钮</button>
		<button type="primary" @click="chooseImg">上传图片</button>
		<image v-for="item in imgArr" :src="item" @click="previewImg(item)"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		onPullDownRefresh() {
			console.log("被拉了");
			uni.stopPullDownRefresh()
		},
		methods: {
			clickHandle(num,e){
				console.log("点击我来",num);
				console.log(e);
			},
			chooseImg(){
				console.log("上传图片");
				uni.chooseImage({
					count:5,
					success:res=>{
						this.imgArr=res.tempFilePaths
					}
				})
			},
			previewImg(current){
				uni.previewImage({
					current,
					urls:this.imgArr,
					loop:true
				})
			}
		}
	}
</script>

<style>

</style>
