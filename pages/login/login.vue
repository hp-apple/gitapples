<template>
	<view class="">
		<view class="pic-bj">
			<image src="../../static/imgs/dengzhu.png" mode=""></image>
		</view>
		<view class="body">
			<form @submit="sublogin">
				<view class="head">
					<view class="back" @tap="back">
						<image src="../../static/imgs/back.png" class="pic-back"></image>
					</view>
					<view class="head-dl" @tap="register">
						注册
					</view>
				</view>
				<view class="hydl">
					欢迎登录
				</view>
				<view class="login">
					<view class="login-yzm" @click="login" :class="{active:isShow==0}">
						验证码登录
					</view>
					<view class="login-zh" @click="login1" :class="{active:isShow==1}">
						账号登录
					</view>
				</view>
				<view class="sjh" v-if="isShow==0">
					<view class="sjh-zh">
						<view class="sjh-zh-mm">
							手机号
						</view>
						<view class="sjh-input">
							<input type="text" value="" placeholder="请输入您的手机号" placeholder-class="placeholder"/>
						</view>
					</view>
					<view class="sjh-mm">
						<view class="sjh-zh-mm">
							短信验证码
						</view>
						<view class="sjh-input send">
							<input type="text" class="code" name="phonecode" v-model="code" placeholder="请输入您的验证码" placeholder-class="placeholder"/>
							<text class="sendtext" @tap="sendcode">{{vcodeBtnName}}</text>
						</view>
					</view>
					<!-- <view class="sjh-wjmm">
						<text>忘记密码?</text>
					</view> -->
				</view>
				<view class="zh" v-if="isShow==1">
					<view class="zh-zh">
						<view class="zh-zh-mm">
							账号
						</view>
						<view class="zh-input">
							<input type="text" value="" placeholder="请输入您的手机号/邮箱" placeholder-class="placeholder"/>
						</view>
					</view>
					<view class="zh-mm">
						<view class="zh-zh-mm">
							密码
						</view>
						<view class="zh-input">
							<input type="text" value="" placeholder="请输入您的密码" placeholder-class="placeholder"/>
						</view>
					</view>
					<view class="zh-wjmm">
						<text @tap="wjmm">忘记密码?</text>
					</view>
				</view>
				<view class="zh-btn">
					<button  class="btn" form-type="submit">立即登录</button>
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
				isShow:1,
				vcodeBtnName: "发送验证码",
			}
		},
		onShow() {
			_this=this;
		},
		methods: {
			login:function(){
				_this.isShow=0;
			},
			login1:function(){
				_this.isShow=1;
			},
			back:function(){
				uni.navigateBack({
					
				})
			},
			register:function(){
				uni.navigateTo({
					url:'/pages/login/register'
				})
			},
			wjmm:function(){
				uni.navigateTo({
					url:'/pages/list/wjmm'
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
			sublogin:function(e){
				uni.switchTab({
					url:'/pages/tabBar/Home/Home'
				})
			}
		}
	}
</script>

<style>
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
/* 返回  注册 */
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
.head-dl{
	font-size: 36upx;
	color: #ea8607;
}
/* 欢迎登录 */
.hydl{
	font-size: 55upx;
	line-height: 100upx;
}
/* 登录方式 */
.login{
	width: 100%;
	display: flex;
	/* background: #007AFF; */
	font-size: 30upx;
	color: #3F536E;
	height: 150upx;
	line-height: 150upx;
}
.login-yzm{
	width: 200upx;
}
.login-zh{
	width: 200upx;
}
.login view.active{
	font-size: 36upx;
	color: #FF951B;
}
/* 验证码登录 */
.sjh{
	width: 100%;
}
.sjh-zh{
	margin-bottom: 50upx;
}
.sjh-zh-mm{
	font-size: 36upx;
	height: 70upx;
	line-height: 70upx;
}
.sjh-input{
	border: 1px solid #f0f0f0;
	border-radius: 15upx;
	background: #FFFFFF;
	/* height: 80upx; */
}
.sjh-input input{
	height: 100upx;
	line-height: 100upx;
	padding: 0 30upx;
}
.placeholder{
	color:#95a0b6;
	background:#ffffff;
}
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
/* 账号登录 */
.zh{
	width: 100%;
	/* background: #007AFF; */
}
.zh-zh{
	margin-bottom: 50upx;
}
.zh-zh-mm{
	font-size: 36upx;
	height: 70upx;
	line-height: 70upx;
}
.zh-input{
	border: 1px solid #F0F0F0;
	border-radius: 15upx;
	background: #FFFFFF;
}
.zh-input input{
	height: 100upx;
	line-height: 100upx;
	padding: 0 30upx;
}
.zh-wjmm{
	width: 100%;
	height: 100upx;
	line-height: 100upx;
	text-align: right;
	color: #999999;
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
