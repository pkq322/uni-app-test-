<template>
	<view>
		<view>
			组件1
		</view>
		<!-- 具名插槽 -->
		<view class="box2">
			<slot name="slot1">
			</slot>
			<view>
				{{"父组件传递过来给子组件的值:"+title}}
			</view>
			<button type="default" @click="sendNum">子组件给父组件传值</button>
		</view>
	</view>
</template>

<script>
	export default {
		name: "test1",
		data() {
			return {
				num: 3
			};
		},
		// 父传子
		props: [
			'title'
		],
		
		methods:{
			sendNum(){
				console.log("给父组件传值");
				this.$emit("sendNum2",this.num)
			}
		},
		beforeCreate() {
			console.log("实例初始化了,数据和dom没有初始化");
			console.log(this.num);
		},

		created() {
			console.log("数据初始化完成", this.num);
		},

		beforeMount() {
			console.log("渲染dom之前");
		},

		mounted() {
			console.log("dom渲染完成");
		}
	}
</script>

<style>
	.box2 {
		color: #007AFF;
	}
</style>
