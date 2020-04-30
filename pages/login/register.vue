<template>
	<view>
		<view class="pic-bj">
			<image src="../../static/imgs/dengzhu.png"></image>
		</view>
		<view class="body">
			<form @submit="zcsubmit">
				<view class="head">
					<view class="back" @tap="back">
						<image src="../../static/imgs/back.png" class="pic-back"></image>
					</view>
					<view class="head-dl" @tap="login">
						登录
					</view>
				</view>
				<view class="zhuce">
					<text>注册</text>
				</view>
				<view class="zc-input">
					<view class="zc-input-box">
						<input type="text" name="mobile" v-model="mobile" placeholder="手机号码/邮箱:" placeholder-class="placeholder"/>
					</view>
					<view class="zc-input-box">
						<input type="text" name="code" v-model="code" placeholder="验证码:" placeholder-class="placeholder"/>
					</view>
					<view class="zc-input-box send">
						<input class="code" type="text" name="phonecode" v-model="code" placeholder="动态验证码:" placeholder-class="placeholder"/>
						<!-- <view class="send-text"> -->
							<text class="sendtext" @tap="sendcode">{{vcodeBtnName}}</text>
						<!-- </view> -->
					</view>
					<view class="zc-input-box">
						<input type="password" name="pwd" v-model="pwd" placeholder="密码:" placeholder-class="placeholder"/>
					</view>
					<view class="zc-input-box">
						<input type="password" name="repwd" v-model="pwd" placeholder="确认密码:" placeholder-class="placeholder"/>
					</view>
					<view class="zc-input-box">
						<input type="text" name="yqcode" v-model="code" placeholder="邀请码(选填):" placeholder-class="placeholder"/>
					</view>
				</view>
				<view class="">
					<button class="btn" formType="confirm">确认注册</button>
				</view>
			</form>
			<form @submit="tanc">
				<view class="" v-show="setpwd==true">
					<view class="fuceng"></view>
					<view class="fc">
						<view class="fc-title">
							<view class="fc-title-con">
								<text>设置交易密码</text>
							</view>
							<view class="fc-title-pic" @tap="guanbi">
								<image src="../../static/imgs/guanbi.png" class="pic-guanbi"></image>
							</view>
						</view>
						<view class="fc-con">
							<view class="fc-con-input">
								<image src="../../static/imgs/pwd.png" class="pic-pwd"></image>
								<input type="password" name="pwd" v-model="pwd" placeholder="请输入您的交易密码" placeholder-class="placeholder tanc"/>
							</view>
							<view class="fc-con-input">
								<image src="../../static/imgs/qrpwd.png" class="pic-pwd"></image>
								<input type="password" name="pwd" v-model="pwd" placeholder="确认交易密码" placeholder-class="placeholder tanc"/>
							</view>
						</view>
						<view class="">
							<button class="submit">提交</button>
						</view>
					</view>
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
				setpwd:false,
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
			confirm:function(){
				// _this.setpwd=true
			},
			guanbi:function(){
				_this.setpwd=false
			},
			login:function(){
				uni.navigateTo({
					url:'/pages/login/login'
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
			// 注册
			zcsubmit:function(e){
				console.log(e)
				var repas=e.detail.value.password;
				// console.log(repas);
				var rule = [
					{name:"mobile", checkType : "phoneno", checkRule:"",  errorMsg:"账号应为手机号"},
					// {name:"code",checkType : "notnull", checkRule:"",  errorMsg:"请填写验证码"},
					{name:"phonecode",checkType : "notnull",checkRule:"",  errorMsg:"请填写验证码"},
					{name:"pwd",checkType : "reg",checkRule:"^(?![0-9]+$)(?![a-zA-Z]+$)[0-9A-Za-z]{8,20}$",errorMsg:"密码不能低于8位数字和字母"},
					{name:"repwd",checkType:"same",checkRule:repas,errorMsg:"密码不一致"},
					{name:"yqcode",checkType : "",checkRule:"",  errorMsg:"请填写邀请码"}
				];
			}
		}
	}
</script>

<style>
/* 注册背景图 */
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
.head-dl{
	font-size: 36upx;
	color: #ea8607;
}
/* 注册 */
.zhuce{
	font-size: 55upx;
	line-height: 100upx;
}
.zc-input{
	
}
.zc-input-box{
	width: 100%;
	border: 1px solid #f0f0f0;
	border-radius: 15upx;
	height: 100upx;
	margin: 20upx auto;
}
.zc-input input{
	height: 100upx;
	line-height: 100upx;
	border-radius: 15upx;
	padding: 0 30upx;
	background: #FFFFFF;
}
.placeholder{
	color:#95a0b6;
	background:#ffffff;
}
.tanc{
	font-size: 28upx;
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
/* 浮层 */
.fuceng{
	position: fixed;
	width: 100%;
	height: 100%;
	top: 0;
	bottom: 0;
	left: 0;
	right: 0;
	background: #000;
	opacity: 0.6;
	z-index: 10001;
}
.fc{
	width: 80%;
	background: #FFFFFF;
	position: fixed;
	height: 500upx;
	left:10%;
	z-index:10002;
	top: 25%;
	border-radius:20rpx;
}
.fc-title{
	width: 100%;
	height: 120upx;
	line-height: 120upx;
	display: flex;
}
.fc-title-con{
	font-size: 36upx;
	text-align: center;
	flex: 1;
}
.fc-title-pic{
	width: 80upx;
	height: 60upx;
}
.fc-con{
	width: 90%;
	margin: 0 auto;
}
.fc-con-input{
	display: flex;
	border-bottom: 1px solid #000000;
	height: 80upx;
	margin: 20upx auto;
	line-height: 80upx;
}
.fc-con-input input{
	height: 80upx;
	line-height: 80upx;
}
.pic-guanbi{
	width: 40upx;
	height: 40upx;
}
.pic-pwd{
	width: 40upx;
	height: 50upx;
	margin: 15upx;
}
.submit{
	width: 90%;
	margin: 50upx auto;
	font-size: 36upx;
	color: #FFFFFF;
	border-radius: 50upx;
	background: #ff951b;
	background: linear-gradient(#ffbc05, #ff951b);
}
</style>
