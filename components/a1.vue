<template>
	<view>
		<button type="default" @click="addNum">这是a修改b组件的值</button>
	</view>
</template>

<script>
	export default {
		name:"a1",
		data() {
			return {
				
			};
		},
		
		methods:{
			addNum(){
				uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
