<template>
	<view>
		<view class="pic-bj">
			<image src="../../static/imgs/dengzhu.png" mode=""></image>
		</view>
		<view class="body">
			<form @submit="fgsubmit">
				<view class="head">
					<view class="back" @tap="back">
						<image src="../../static/imgs/back.png" class="pic-back"></image>
					</view>
				</view>
				<view class="wjmm">
					<text>忘记密码</text>
				</view>
				<view class="wjmm-input">
					<view class="wjmm-input-box">
						<input type="text" value="" placeholder="手机号码/邮箱:" placeholder-style="color:#95a0b6;background:#ffffff"/>
					</view>
					<view class="wjmm-input-box send">
						<input type="text" class="code" name="phonecode" v-model="code" placeholder="验证码:" placeholder-style="color:#95a0b6;background:#ffffff"/>
						<text class="sendtext" @tap="sendcode">{{vcodeBtnName}}</text>
					</view>
					<view class="wjmm-input-box">
						<input type="text" value="" placeholder="新的密码:" placeholder-style="color:#95a0b6;background:#ffffff"/>
					</view>
					<view class="wjmm-input-box">
						<input type="text" value="" placeholder="确认密码:" placeholder-style="color:#95a0b6;background:#ffffff"/>
					</view>
				</view>
				<view class="">
					<button class="btn">确认修改</button>
				</view>
			</form>
		</view>
	</view>
</template>

<script>
	var _this;
	export default {
		data() {
			return {
				vcodeBtnName: "发送验证码",
			}
		},
		onShow() {
			_this=this;
			// _this.sendcode()
		},
		methods: {
			back:function(){
				uni.navigateBack({
					
				})
			},
			// 发送验证码
			// sendcode:function(){
			// 	var myreg = /^(13[0-9]|14[579]|15[0-3,5-9]|16[6]|17[0135678]|18[0-9]|19[89])\d{8}$/;
			// 	if (!myreg.test(this.mobile)) {
			// 		uni.showToast({
			// 			title: '请正确填写手机号码',
			// 			icon: "none"
			// 		});
			// 		return false;
			// 	}
			// 	if (this.vcodeBtnName != '发送验证码' && this.vcodeBtnName != '重新发送') {
			// 		return;
			// 	}
			// },
		}
	}

</script>

<style>
/* 背景图 */
.pic-bj{
	width: 100%;
	position: fixed;
	z-index: -1;
}
.pic-bj image{
	width: 100%;
}
.body{
	width: 90%;
	margin: 0 auto;
}
.head{
	width: 100%;
	/* background: #4CD964; */
	height: 80upx;
	padding-top: 70upx;
	line-height: 80upx;
	display: flex;
	justify-content: space-between;
}
.back{
	width: 60upx;
	height: 40upx;
}
.pic-back{
	width: 60upx;
	height: 40upx;
	margin: 25upx 0;
}
/* 忘记密码 */
.wjmm{
	font-size: 55upx;
	line-height: 100upx;
}
.wjmm-input{
	
}
.wjmm-input-box{
	width: 100%;
	border: 1px solid #F0F0F0;
	margin: 20upx auto;
	border-radius: 15upx;
	background: #FFFFFF;
}
.wjmm-input input{
	height: 100upx;
	line-height: 100upx;
	padding: 0 30upx;
}
/* 发送验证码 */
.send{
	display: flex;
	flex-wrap: nowrap;
}
.code{
	width: 60%;
}
.sendtext{
	font-size:30upx;
	color: #FFFFFF;
	background: #FF991E;
	height: 50upx;
	line-height: 50upx;
	border-radius: 50upx;
	margin: 25upx 15upx;
	padding:0 15upx;
}
.btn{
	width: 100%;
	color: #FFFFFF;
	font-size: 36upx;
	text-align: center;
	font-weight: 600;
	background: #ff951b;
	background: linear-gradient(to right,#ffbc05, #ff951b);
	margin: 80upx 0;
	border-radius: 50upx;
}
</style>
