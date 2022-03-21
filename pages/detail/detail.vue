<template>
	<view>
		<view>
			<text>唱跳打篮球</text>
		</view>
		<view>
			<text selectable>唱跳打篮球</text>
		</view>
		<view>
			<text selectable space="emsp">唱跳 打篮球</text>
		</view>
		<view>
			<text>&amp;</text>
		</view>
		<view class="box-root" hover-class="box-root-active">
			<view class="box" hover-class="box-active" hover-stop-propagation :hover-start-time="2000"
				:hover-stay-time="2000">
				<!-- hover-stop-propagation 阻止冒泡 -->
				我是一个盒子
			</view>
		</view>
		<button>按钮</button>
		<button size="mini" type="primary">按钮</button>
		<button size="mini" type="primary" plain>按钮</button>
		<button size="mini" type="primary" plain disabled>按钮</button>
		<button size="mini" type="primary" plain disabled loading>按钮</button>
		
		
		<image src="../../static/logo.png"></image>
		<image src="../../static/logo.png" mode="scaleToFill"></image>
		<image src="../../static/logo.png" mode="aspectFit"></image>
		<image src="../../static/logo.png" mode="aspectFill"></image>
	</view>
</template>

<script>
	export default {
		onLoad(option) {
			console.log(option);
		},
		data() {
			return {
				
			}
		},
		methods: {

		}
	}
</script>

<style>
	.box-root {
		width: 200px;
		height: 200px;
		background-color: #4CD964;
	}

	.box {
		width: 100px;
		height: 100px;
		background-color: #007AFF;
	}

	.box-root-active {
		background-color: #DD524D;
	}

	.box-active {
		background-color: red;
	}
</style>
