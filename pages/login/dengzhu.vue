<template>
	<view>
		<view class="pic-dz">
			<image src="../../static/imgs/szjypt.png"></image>
		</view>
		<view class="dz">
			<view class="dz-deng" @tap="login">
				登录
			</view>
			<view class="dz-zhu" @tap="register">
				注册
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			login:function(){
				uni.navigateTo({
					url:'/pages/login/login'
				})
			},
			register:function(){
				uni.navigateTo({
					url:'/pages/login/register'
				})
			}
		}
	}
</script>

<style>
body{
	/* display: flex; */
}
.pic-dz{
	width: 100%;
	height:100vh;
	/* background: #007AFF; */
}
.pic-dz image{
	width: 100%;
	height: 100%;
}
.dz{
	width: 94%;
	position: absolute;
	top:80%;
	margin: 0 25upx;
	display: flex;
	justify-content: space-around;
	text-align: center;
}
.dz-deng{
	/* font-size: 40upx; */
	font-weight: 600;
	width: 40%;
	height: 80upx;
	line-height: 80upx;
	border: 1px solid #000000;
}
.dz-zhu{
	width: 40%;
	font-weight: 600;
	color: #FFFFFF;
	height: 80upx;
	line-height: 80upx;
	border: 1px solid #ff991e;
	background: #FF991E;
}
</style>
