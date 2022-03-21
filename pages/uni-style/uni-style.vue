<template>
	<view>
		<view>
			样式学习
		</view>
		<view class="box1">
			测试文字
			<text>scss(test)</text>
		</view>
		<view class="iconfont icon-gongwenbao">
		</view>
		<test :title="title" @sendNum2="sendNum3">
			<template #slot1>
				<text>插槽的使用</text>
				<view>
					子组件传递过来给父组件的值:{{num}}
				</view>
			</template>
		</test>
		<test-a></test-a>
		<test-b></test-b>
		<uni-calendar 
		    :insert="true"
		    :lunar="true" 
		    :start-date="'2019-3-2'"
		    :end-date="'2019-5-20'"
		    @change="change"
		     />
	</view>

</template>

<script>
	// 导入组件
	import test from '../../components/test1.vue'
	import testA from '../../components/a1.vue'
	import testB from '../../components/b1.vue'
	import uniCalendar from'@/components/uni-calendar/uni-calendar.vue'
	export default {
		data() {
			return {
				title: "hello",
				num: 0
			}
		},
		methods: {
			sendNum3(num) {
				console.log(num);
				this.num = num
			},
			
			change(){
				console.log("触发了change");
			}
		},
		components: {
			test,
			testA,
			testB,
			uniCalendar
		}
	}
</script>

<style lang="scss">
	@import url("./a.css");

	.box1 {
		width: 375rpx;
		height: 375rpx;
		/* background: #007AFF; */
		font-size: 40rpx;
		color: #333333;

		text {
			color: #007AFF;
		}
	}
</style>
