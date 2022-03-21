<template>
	<view>
		<view>
			这是列表页
		</view>
		<button type="default" @click="get">发送get请求</button>
		<button type="default" @click="setStorage">存储数据</button>
		<button type="default" @click="getStorage">获取数据</button>
		<button type="default" @click="removeId">移除id数据</button>
		<view class="box-item" v-for="(item,index) in list" :key="index">
			{{item}}
		</view>
		<!-- <button type="default" @click="pullDown">下拉刷新</button> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					"前端", "ui", "java", "大数据", "测试"
				]
			}
		},

		onPullDownRefresh() {
			console.log("触发了下拉刷新");
			setTimeout(() => {
				this.list = [111, 222, 333, 444, 555]
				uni.stopPullDownRefresh() //停止下拉刷新
			}, 2000)
		},

		onReachBottom() {
			console.log("页面触底了");
			this.list = [...this.list, ...[123, 456, 789, 123, 456, 789]]
		},

		methods: {
			pullDown() {
				uni.startPullDownRefresh()
			},

			get() {
				uni.request({
					url: "http://localhost:8082/api/getlunbo",
					success(res) {
						console.log(res);
					}
				})
			},
			
			//存储数据
			setStorage(){
				// uni.setStorage({
				// 	key:'id',
				// 	data:80,
				// 	success() {
				// 		console.log('存储成功');
				// 	}
				// })
				uni.setStorageSync("id",100)
			},
			
			//获取数据
			getStorage(){
				// uni.getStorage({
				// 	key:"id",
				// 	success(res){
				// 		console.log("获取成功",res.data);
				// 	}
				// })
				const res = uni.getStorageSync("id")
				console.log(res);
			},
			
			//删除指定id数据
			removeId(){
				// uni.removeStorage({
				// 	key:"id",
				// 	success() {
				// 		console.log("删除成功");
				// 	}
				// })
				uni.removeStorageSync("id")
			}
		}
	}
</script>

<style>
	.box-item {
		height: 200px;
		line-height: 150px;
	}
</style>
