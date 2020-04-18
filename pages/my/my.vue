<template>
	<view class="content">
		<view class="top">
			<image class="img" src="../../static/morentouxiangico.png" mode="widthFix"></image>
			<view class="info">
				<view class="infoname">小黄鸭</view>
				<view class="infosex">北京 / 男 / 24</view>
				<view class="infocontent">这个家伙很懒，什么也没留下。</view>
			</view>
		</view>
		
		<view class="fuwu">我的服务</view>
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; "
		 @click="xinxiguanli()">
			<image src="../../static/wodexinxiguanliico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">用户信息管理</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; "
		 @click="shangwangzhanghaoguanli()">
			<image src="../../static/shangwangzhuanghaoico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">上网账号管理</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; "
		 @click="iptvguanli()">
			<image src="../../static/iptvguanliico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">IPTV账号管理</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		
		
		
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; margin-top: 20rpx;"
		 @click="chongzhijilu()">
			<image src="../../static/chongzhijiluico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">充值记录管理</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; "
		 @click="kefudianhua()">
			<image src="../../static/kefudianhuaico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">电话客服</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		<view style="display: flex; flex-direction: row; align-items: center; width: 100%; height: 90rpx; background-color: #FFFFFF; border-bottom: 2rpx solid #F7F7F7; "
		 @click="wodeyonghuxieyi()">
			<image src="../../static/wodeyonghuxieyiico.png"
			 mode="widthFix" style="margin-left: 30rpx; width: 35rpx; height: 35rpx;"></image>
			<view style="flex: 1; font-size: 28rpx; color: #363636;margin-left: 30rpx;">用户协议</view>
			<view style="width: 100rpx; text-align: center;">
				<image src="../../static/jiantouyouixo.png" mode="aspectFit" style="width:15rpx;"></image>
			</view>
		</view>
		
		<view style="border-radius: 50upx; width: 60%; margin-left: 20%; height: 80upx; line-height: 80upx; text-align: center; background-color: #1d89ff; color: #FFFFFF; font-size: 30upx; margin-top: 150upx;"
		 @click="tuichudenglu">退出登录</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {

			}
		},
		onLoad: function(e) {
			that = this;
			
		},
		onShow: function(res) {

		},
		methods: {
			xinxiguanli: function(pos){
				var token = uni.getStorageSync('token');
				if (token == '' || token == null) {
					uni.showModal({
						cancelText: '取消登录',
						confirmText: '立即登陆',
						title: '提示',
						content: '是否确定授权登陆？',
						success: function(res) {
							if (res.confirm) {
								uni.navigateTo({
									url: '../login/login'
								})
							} else if (res.cancel) {
								console.log('用户点击取消');
							}
						}
					})
					return
				}
				
				uni.navigateTo({
					url:'./usermanager'
				})
			},
			shangwangzhanghaoguanli: function(pos){
				var token = uni.getStorageSync('token');
				if (token == '' || token == null) {
					uni.showModal({
						cancelText: '取消登录',
						confirmText: '立即登陆',
						title: '提示',
						content: '是否确定授权登陆？',
						success: function(res) {
							if (res.confirm) {
								uni.navigateTo({
									url: '../login/login'
								})
							} else if (res.cancel) {
								console.log('用户点击取消');
							}
						}
					})
					return
				}
				uni.navigateTo({
					url:'./shangwangzhanghaoguanli'
				})
			},
			iptvguanli: function(pos){
				var token = uni.getStorageSync('token');
				if (token == '' || token == null) {
					uni.showModal({
						cancelText: '取消登录',
						confirmText: '立即登陆',
						title: '提示',
						content: '是否确定授权登陆？',
						success: function(res) {
							if (res.confirm) {
								uni.navigateTo({
									url: '../login/login'
								})
							} else if (res.cancel) {
								console.log('用户点击取消');
							}
						}
					})
					return
				}
				uni.navigateTo({
					url:'./iptvzhanghaoguanli'
				})
			},
			chongzhijilu: function(pos){
				var token = uni.getStorageSync('token');
				if (token == '' || token == null) {
					uni.showModal({
						cancelText: '取消登录',
						confirmText: '立即登陆',
						title: '提示',
						content: '是否确定授权登陆？',
						success: function(res) {
							if (res.confirm) {
								uni.navigateTo({
									url: '../login/login'
								})
							} else if (res.cancel) {
								console.log('用户点击取消');
							}
						}
					})
					return
				}
				uni.navigateTo({
					url:'./chongzhijilu'
				})
			},
			kefudianhua: function(pos){
				uni.makePhoneCall({
				    phoneNumber: '18191217921' 
				});
			},
			wodeyonghuxieyi: function(pos){
				var token = uni.getStorageSync('token');
				console.log('token：' + token);
				if (token == '' || token == null) {
					uni.showModal({
						cancelText: '取消登录',
						confirmText: '立即登陆',
						title: '提示',
						content: '是否确定授权登陆？',
						success: function(res) {
							if (res.confirm) {
								uni.navigateTo({
									url: '../login/login'
								})
							} else if (res.cancel) {
								console.log('用户点击取消');
							}
						}
					})
					return
				}
				
				uni.showToast({
					title:'请提供协议内容'
				})
			},
			tuichudenglu: function(pos){
				uni.showModal({
					title: '退出账号',
					content: '确定要退出当前 账号吗？',
					confirmColor: '#1d89ff',
					success: function(res) {
						if (res.confirm) {
							try {
								uni.clearStorageSync();
								uni.navigateTo({
									url: '../login/login'
								})
							} catch (e) {
								console.log('清除缓存错误：' + e);
							}
						}
					}
				});
			}

		}

	}
</script>

<style>
	page {
		background-color: #F7F7F7;
	}

	.content {
		display: flex;
		flex-direction: column;
		width: 100%;
	}

	.top {
		width: 100%;
		height: 250upx;
		display: flex;
		flex-direction: row;
		background-image: url(../../static/wodebeijingico.png);
	}

	.img {
		width: 140upx;
		height: 140upx;
		margin: 55upx 40upx 55upx 30upx;
		border-radius: 50%;
	}

	.info {
		display: flex;
		flex-direction: column;
		flex: 1;
		padding: 65upx 100upx 0upx 0upx;
	}

	.infoname {
		width: 100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 28rpx;
		font-weight: 700;
		color: #333333;
		text-overflow: ellipsis;
		overflow: hidden;

	}

	.infosex {
		width: 100%;
		height: 40upx;
		line-height: 40upx;
		font-size: 24upx;
		color: #333333;
		text-overflow: ellipsis;
		overflow: hidden;
	}

	.infocontent {
		width: 100%;
		height: 40upx;
		line-height: 40upx;
		font-size: 24upx;
		color: #7c7c7c;
		text-overflow: ellipsis;
		overflow: hidden;
	}
	.fuwu {
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		font-size: 30upx;
		font-weight: 700;
		padding-left: 30rpx;
		color: #333333;
	}
</style>
