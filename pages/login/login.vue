<template>
	<view class="content">
		<input style="margin-top: 300upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="number" placeholder="手机号码" confirm-type="done" v-model="zhanghao"></input>
		<input style="margin-top: 40upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="登录密码" confirm-type="done" password="true" v-model="mima"></input>

		<view style="padding: 30upx; color: #1d89ff; font-size: 24upx; margin-top: 250upx;" @click="zhuce">新用户注册</view>
		<view style="padding: 30upx; color: #1d89ff; font-size: 24upx;" @click="wangjimima">忘记密码</view>
		<view style="border-radius: 50upx; padding: 20upx 125upx; background-color: #1d89ff; color: #FFFFFF; font-size: 30upx; margin-top: 100upx;"
		 @click="lijidenglu">立即登陆</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				zhanghao: '',
				mima: ''

			}
		},
		onLoad: function(e) {
			that = this;
			
		},
		onShow: function(res) {

		},
		methods: {
			zhuce: function() {
				uni.navigateTo({
					url: './zhuce'
				})
			},
			wangjimima: function() {
				uni.navigateTo({
					url: './wangjimima'
				})
			},
			lijidenglu: function() {
				if(!that.zhanghao){
					uni.showToast({
						title:'请输入账号'
					})
					
					return
				}
				if(!that.mima){
					uni.showToast({
						title:'请输入密码'
					})
					
					return
				}
				try {
					uni.setStorageSync('token', '1234567890');
					uni.navigateBack({
						delta: 1
					})
				} catch (e) {
					// error
				}

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
		align-items: center;
	}
</style>
