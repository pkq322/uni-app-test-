<template>
	<view class>
		<view>
			上传图片
		</view>
		<button type="default" @click="chooseImg">上传图片</button>
		<image v-for="(item,index) in imgArr" :key="index" :src="item" mode="aspectFill" @click="previewImg(item)"></image>
		<!-- #ifdef H5 -->
		<view>
			仅在h5中显示
		</view> 
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
		<view>
			仅在小程序中显示
		</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		methods: {
			
			//上传图片
			chooseImg(){
				uni.chooseImage({
					count:5,   //最多上传几张
					success:res => {
						console.log(res);
						this.imgArr = res.tempFilePaths
					}
				})
			},
			
			//预览图片
			previewImg(current){
				uni.previewImage({
					current:current,   //当前点击的图片
					urls:this.imgArr,  //图片地址
					loop:true,         //滑动时循环图片
					indicator:'number'
				})
			},
		},
		onLoad() {
			// #ifdef H5
			console.log('仅在h5页面显示');
			// #endif
			// #ifdef MP-WEIXIN
			console.log('仅在微信小程序页面显示');
			// #endif
		}
	}
</script>

<style>
	/* #ifdef H5 */
	view{
		color: pink;
	}
 /* #endif */
 
 /* #ifdef MP-WEIXIN */
	view{
		color: #007AFF;
	}
	/* #endif */
</style>
