<template>
	<view>
		这是b组件的数据:{{num}}
	</view>
</template>

<script>
	export default {
		name:"b1",
		data() {
			return {
				num:0
			};
		},
		
		created() {
			// 注册一个全局的事件
			uni.$on('updateNum',num=> {
				this.num+=num
			})
		}
	}
</script>

<style>

</style>
