<template>
	<view>
		<view>
			数据绑定的学习
		</view>
		<view>
			{{msg}}
		</view>
		<view>
			{{flag?"我是真的":"我是假的"}}
		</view>
		<image :src="src" mode=""></image>
		<view v-for="(item,index) in arr" :key="item.id">
			序号:{{item.id}}
			姓名:{{item.name}}
			年龄:{{item.age}}
		</view>
		<button type="default" @click="handle($event,33)">按钮</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg: "hello",
				flag: true,
				src: "../../static/logo.png",
				arr: [{
						name: "小明",
						age: 16,
						id: 1
					},
					{
						name: "小红",
						age: 56,
						id: 2
					},
					{
						name: "小开",
						age: 78,
						id: 3
					}
				]
			}
		},
		methods: {
			handle(e,num){
				console.log(123);
				console.log(e);
				console.log(num);
			}
		},
		onLoad(option) {
			console.log("页面加载了",option);
		},
		onShow() {
			console.log("页面显示了");
		},
		onReady() {
			console.log("页面初次渲染完毕");
		},
		onHide() {
			console.log("页面隐藏了");
		}
	}
</script>

<style>

</style>
