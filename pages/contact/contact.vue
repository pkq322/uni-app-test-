<template>
	<view>
		<view>
			导航跳转的学习
		</view>
		<!-- 声明式导航 -->
		<!-- 不能跳转到tabbar页 -->
		<navigator url="/pages/detail/detail?id=80&age=18">跳转至详情页</navigator>
		<!-- 可跳转到tabbar -->
		<navigator url="../list/list" open-type="switchTab">跳转到list页</navigator>
		<navigator url="../detail/detail" open-type="redirect">跳转至详情页</navigator>
		<!-- 编程式导航 -->
		<button type="default" @click="godetail">跳转到详情页</button>
		<button type="default" @click="golist">跳转到list页</button>
		<button type="default" @click="redirectDetail">跳转到详情页并关闭当前页面</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onUnload() {
			console.log("导航卸载了");
		},
		methods: {
			godetail(){
				uni.navigateTo({
					url:"../detail/detail?id=90&age=28"
				})
			},
			golist(){
				uni.switchTab({
					url:"../list/list"
				})
			},
			redirectDetail(){
				uni.redirectTo({
					url:"../detail/detail"
				})
			}
		}
	}
</script>

<style>

</style>
