<template>
	<view class="content">
		<input style="margin-top: 200upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="number" placeholder="手机号码" confirm-type="done" v-model="zhanghao"></input>
		<view style="display: flex; flex-direction: row; margin-top: 40upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx;  border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;">
			<input style="width: 60%; height: 90upx; line-height: 90upx; text-align: left; font-size: 28upx; color: #555555;"
			 type="number" placeholder="验证码" confirm-type="done" v-model="mima0"></input>
			<view style="width: 40%; height: 90upx; line-height: 90upx; text-align: right; font-size: 24upx; color: #1d89ff;"
			 @click="yanzhengma">{{strtime}}</view>
		</view>
		<input style="margin-top: 40upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="重置密码" confirm-type="done" password="true" v-model="mima1"></input>
		<input style="margin-top: 40upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="确认密码" confirm-type="done" password="true" v-model="mima2"></input>

		<view style="border-radius: 50upx; padding: 20upx 125upx; background-color: #1d89ff; color: #FFFFFF; font-size: 30upx; margin-top: 150upx;"
		 @click="lijidenglu">确认重置</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				intervalID: 0,
				havetime: 60,
				zhanghao: '',
				mima0: '',
				mima1: '',
				mima2: '',
				strtime: '获取验证码',
				state: 0

			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {

		},
		onUnload() {
			console.log('页面卸载')
			clearInterval(that.intervalID)
		},
		methods: {

			lijidenglu: function() {
				if (!that.zhanghao) {
					uni.showToast({
						title: '请输入账号'
					})

					return
				}
				if (!that.mima0) {
					uni.showToast({
						title: '请输入验证码'
					})

					return
				}
				if (!that.mima1) {
					uni.showToast({
						title: '请输入密码'
					})
				
					return
				}
				if (!that.mima2) {
					uni.showToast({
						title: '请输入确认密码'
					})
				
					return
				}
				if (that.mima2 != that.mima1) {
					uni.showToast({
						title: '两次密码不一致'
					})
				
					return
				}
				uni.navigateBack({
					delta: 1
				})
			},

			yanzhengma: function() {
				console.log(that.zhanghao)
				if (that.state == 1) {
					return
				}
				if (!that.zhanghao) {
					uni.showToast({
						title: '请输入账号'
					})
					return
				}
				that.state = 1;
				that.intervalID = setInterval(function() {
					that.havetime--;
					if (that.havetime > 0) {
						that.strtime = that.havetime + 'S后获取'
					} else {
						clearInterval(that.intervalID)
						that.state = 0;
						that.havetime = 60;
						that.strtime = '获取验证码'
					}
				}, 1000)

			},

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
