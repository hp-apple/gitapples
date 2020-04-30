<template>
	<view>
		<view class="header">
			<view class="head">
				<text class="head-tit">首页</text>
				<view class="head-right">
					<image src="../../../static/imgs/tongzhi.png" class="pic-tz"></image>
				</view>
			</view>
			<!-- <view class="">
				<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
					<swiper-item>
						<image src="../../../static/imgs/ad.png" mode=""></image>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item"></view>
					</swiper-item>
				</swiper>
			</view> -->
		</view>
		<view class="dh">
			<view class="dh-box">
				<image src="../../../static/imgs/cb.png" class="pic-dh"></image>
				<text>充币</text>
			</view>
			<view class="dh-box">
				<image src="../../../static/imgs/gd.png" class="pic-dh"></image>
				<text>跟单</text>
			</view>
			<view class="dh-box">
				<image src="../../../static/imgs/phb.png" class="pic-dh"></image>
				<text>排行榜</text>
			</view>
			<view class="dh-box">
				<image src="../../../static/imgs/yqyj.png" class="pic-dh"></image>
				<text>邀请有奖</text>
			</view>
		</view>
		<view class="ad-gg">
			<view class="ad-gg-ad">
				<image src="../../../static/imgs/ad.png" class="pic-ad"></image>
			</view>
			<view class="ad-gg-gg">
				<view class="">
					<image src="../../../static/imgs/gonggao.png" class="pic-gg"></image>
				</view>
				<text>关于调整包币交易区普通用户单笔最高限额的公告</text>
			</view>
		</view>
		<view class="kongbai">
			
		</view>
		<view class="bijia">
			<view class="bijia-title">
				<view class="color">
					
				</view>
				<text>币价</text>
			</view>
			<view class="bijia-bj">
				<view class="bijia-bj-box">
					<text class="col-title">TWD/USDT</text>
					<text class="col-mid">15056</text>
					<text class="col-per">+5.32%</text>
				</view>
				<view class="bijia-bj-box">
					<text class="col-title">USD/USDT</text>
					<text class="col-mid">58484</text>
					<text class="col-per">-5.23%</text>
				</view>
				<view class="bijia-bj-box">
					<text class="col-title">CNY/USDT</text>
					<text class="col-mid">15465</text>
					<text class="col-per">+5.22%</text>
				</view>
			</view>
		</view>
		<view class="kongbai">
			
		</view>
		<view class="bd">
			<view class="bd-title">
				<view class="zhang" @click="bang" :class="{active:isShow==0}">
					涨幅榜
				</view>
				<view class="die" @click="bang1" :class="{active:isShow==1}">
					跌幅榜
				</view>
			</view>
			<view class="bd-con" v-if="isShow==0">
				<view class="bd-con-box" ><!-- v-for="(item,index) in hangqing" :key="index" -->
					<view class="bd-con-box-l">
						<text style="font-size: 35upx;">TWD/BTC</text>
						<text>Vol0.45k</text>
					</view>
					<view class="bd-con-box-m">
						<text style="color: #07c087;font-size: 35upx;">0.1215</text>
						<text>￥255</text>
					</view>
					<view class="bd-con-box-r">
						<button class="bd-btn-z">+15.22%</button>
					</view>
				</view>
			</view>
			<view class="bd-con" v-else>
				<view class="bd-con-box" ><!-- v-for="(item,index) in hangqing" :key="index" -->
					<view class="bd-con-box-l">
						<text style="font-size: 35upx;">TWD/BTC</text>
						<text>Vol254.00k</text>
					</view>
					<view class="bd-con-box-m">
						<text style="font-size: 35upx;color: #07c087;">0.41854</text>
						<text>￥14</text>
					</view>
					<view class="bd-con-box-r">
						<button class="bd-btn-d">-5.22%</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	var _this;
	export default {
		data() {
			return {
				isShow:0,
			}
		},
		onShow() {
			_this=this;
		},
		methods: {
			bang: function() {
				_this.isShow = 0;
			},
			bang1: function() {
				_this.isShow = 1;
			},
		}
	}
</script>

<style>
.header{
	width: 100%;
	height: 500upx;
	background: #FF951B;
}
.head{
	width: 100%;
	display: flex;
	height: 80upx;
	padding-top: 50upx;
	position: fixed;
	top: 0;
}
.head-tit{
	text-align: center;
	color: #FFFFFF;
	flex: 1;
	font-size: 36upx;
	height: 80upx;
	line-height: 80upx;
}
.head-right{
	height: 80upx;
	line-height: 80upx;
	z-index: 100;
	margin: 15upx;
}
.pic-tz{
	width: 40upx;
	height: 50upx;
}
/* 导航 */
.dh{
	width: 94%;
	margin: 0 auto;
	/* background: #007AFF; */
	display: flex;
	justify-content: space-around;
}
.dh-box{
	width: 20%;
	height: 150upx;
	text-align: center;
	/* background-color: #4CD964; */
}
.dh-box image{
	/* height: 90upx; */
}
.pic-dh{
	width: 50upx;
	height: 50upx;
	margin: 0 auto;
	display: block;
	margin-top: 30upx;
}
.dh-box text{
	line-height: 80upx;
	/* text-align: center; */
}
/* 广告-公告 */
.ad-gg{
	width: 94%;
	margin: 0 auto;
	/* background: #999999; */
}
.ad-gg-ad{
	width: 100%;
	margin: 20upx 0;
}
.pic-ad{
	width: 100%;
	height: 135upx;
}
.ad-gg-gg{
	width: 100%;
	height: 70upx;
	font-size: 26upx;
	/* background-color: #00ff00; */
	display: flex;
}
.ad-gg-gg text{
	line-height: 70upx;
	height: 70upx;
}
.pic-gg{
	width: 50upx;
	height: 35upx;
	margin: 17upx auto;
}
.kongbai{
	width: 100%;
	height: 25upx;
	background: #f8f8f8;
}
/* 币价 */
.bijia{
	width: 100%;
	/* background: #DD524D; */
}
.bijia-title{
	width: 100%;
	line-height: 80upx;
	display: flex;
	font-size: 34upx;
}
.color{
	width: 10upx;
	height: 35upx;
	margin: 25upx 6upx;
	background: #F0AD4E;
	border-radius: 25upx;
}
.bijia-bj{
	width: 94%;
	margin: 10upx auto 30upx;
	display: flex;
}
.bijia-bj-box{
	width: 33%;
}
.col-title{
	color: #F0AD4E;
	font-size: 28upx;
}
.col-mid{
	font-size: 34upx;
	font-weight: 600;
}
.col-per{
	color: #007AFF;
	font-size: 26upx;
}
.bijia-bj-box text{
	display: block;
	text-align: center;
}
/* 涨跌幅 */
.bd{
	width: 94%;
	margin: 0 auto;
}
.bd-title{
	width: 100%;
	height: 60upx;
	line-height: 60upx;
	margin-top: 20upx;
	/* background: #007AFF; */
	display: flex;
	border-bottom: 5px solid #F0AD4E;
}
.bd-title view{
	width: 150upx;
	text-align: center;
	background: #4CD964;
	border-radius: 30upx 0 30upx 0;
	margin-right: 30upx;
	/* border-right: 37px solid transparent; */
}
.bd-title view.active{
	width: 150upx;
	text-align: center;
	background: #F0AD4E;
	border-radius: 30upx 0 0 0;
}
.bd-con{
	width: 100%;
	height: 100upx;
}
.bd-con-box{
	margin: 20upx 0;
	display: flex;
	justify-content: space-between;
}
.bd-con-box-l{
	width: 35%;
}
.bd-con-box-m{
	width: 40%;
}
.bd-con-box-r{
	width: 25%;
}
.bd-con-box text{
	display:block;
	line-height: 40upx;
}
.bd-btn-z{
	background: #07c087;
	color: #FFFFFF;
	/* width: 80%; */
	/* height: 40upx; */
}
.bd-btn-d{
	background: #ff0000;
	color: #FFFFFF;
}
</style>
