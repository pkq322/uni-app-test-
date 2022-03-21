<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		onError:function(err){
			console.log("出现异常了",err);
		}
	}
</script>

<style>
	/*每个页面公共css */
	/* 字体图标的使用 */
	@import url("./static/font/iconfont.css");
	.box1{
		background-color: pink;
	}
</style>
