<template>
	<view class="content">
		<input style="margin-top: 60upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="姓名" confirm-type="done" v-model="strname"></input>
		<input style="margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="number" placeholder="手机号码" confirm-type="done" v-model="zhanghao"></input>
		<view style="display: flex; flex-direction: row; margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx;  border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;">
			<input style="width: 60%; height: 90upx; line-height: 90upx; text-align: left; font-size: 28upx; color: #555555;"
			 type="number" placeholder="验证码" confirm-type="done" v-model="yanzhengmacode"></input>
			<view style="width: 40%; height: 90upx; line-height: 90upx; text-align: right; font-size: 24upx; color: #1d89ff;"
			 @click="yanzhengma">{{strtime}}</view>
		</view>
		<input style="margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="学号" confirm-type="done" v-model="xuehao"></input>
		<input style="margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="证件号码" confirm-type="done" v-model="zhengjianhaoma"></input>
		<view style="display: flex; flex-direction: row; margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; align-items: center; padding-left: 50upx; padding-right: 50upx;  border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 @click="selectquyu">
			<input style="  flex: 1; height: 90upx; line-height: 90upx; text-align: left; font-size: 28upx; color: #555555; "
			 type="text" placeholder="所在地域" confirm-type="done" v-model="diyu" disabled="true"></input>
			<image style="width: 30upx;" mode="aspectFit" src="../../static/xialajiantouico.png"></image>
		</view>
		<input style="margin-top: 25upx;  width: 80%; height: 90upx; line-height: 90upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
		 type="text" placeholder="登陆密码" confirm-type="done" password="true" v-model="mima"></input>

		<view style="display: flex; flex-direction: row; margin-top: 25upx;  margin-left: 7.5%; margin-right: 7.5%;">
			<view style="width: 40%; height: 60upx; line-height: 60upx; text-align: left; color: #4b4b4b; font-size: 26upx; ">初始上网账号数量</view>
			<input style="flex: 1; margin-left: 10upx; margin-right: 10upx; height: 60upx; line-height: 60upx; text-align: center;  font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="number" confirm-type="done" v-model="wangshuliang"></input>

			<view style="display: flex; flex-direction: row; height: 60upx;  width: 25%;  padding-left: 50upx; padding-right: 50upx;  border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF; align-items: center;"
			 @click="selectwangsu">
				<input style="  flex: 1; height: 60upx; line-height: 60upx; text-align: left; font-size: 28upx; color: #555555; "
				 type="text" confirm-type="done" v-model="wangsu" disabled="true"></input>
				<image style="width: 30upx;" mode="aspectFit" src="../../static/xialajiantouico.png"></image>
			</view>

		</view>
		<view style="display: flex; flex-direction: row; margin-top: 25upx;  margin-left: 7.5%; margin-right: 7.5%;">
			<view style="width: 40%; height: 60upx; line-height: 60upx; text-align: left; color: #4b4b4b; font-size: 26upx; ">初始IPTV账号数量</view>
			<input style="flex: 1; margin-left: 10upx; margin-right: 10upx; height: 60upx; line-height: 60upx; text-align: center;  font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="number" confirm-type="done" v-model="iptvshuliang"></input>
			<view style="display: flex; flex-direction: row; height: 60upx;  width: 25%;  padding-left: 50upx; padding-right: 50upx; ">
			</view>
		</view>
		<view style="width: 80%;  display: flex; flex-direction: row; margin-top: 100upx;">
			<view style="border-radius: 50upx; height: 70upx; line-height: 70upx; flex: 1; background-color: #ffffff; color: #1d89ff; font-size: 30upx; text-align: center;"
			 @click="quxiaozhuce">取消</view>
			<view style="width: 30upx; height: 50upx;"></view>
			<view style="border-radius: 50upx;  height: 70upx; line-height: 70upx; flex: 1; background-color: #1d89ff; color: #FFFFFF; font-size: 30upx; text-align: center;"
			 @click="lijizhuce">立即注册</view>
		</view>

	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				intervalID: 0,
				havetime: 60,
				strname: '',
				zhanghao: '',
				yanzhengmacode: '',
				xuehao: '',
				zhengjianhaoma: '',
				diyu: '',
				mima: '',
				strtime: '获取验证码',
				state: 0,
				quyulist: ['西安交通大学', '西北工业大学', '西安音乐学院'],
				wangsulist: ['100M', '200M', '500M'],
				wangsu: '100M',
				wangshuliang: '1',
				iptvshuliang: '0'

			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {

		},
		onUnload() {
			clearInterval(that.intervalID)
		},
		methods: {
			quxiaozhuce: function() {
				uni.navigateBack({
					delta: 1
				})
			},
			selectwangsu: function() {
				uni.showActionSheet({
					itemList: that.wangsulist,
					itemColor: '#838383',
					success: function(res) {
						that.wangsu = that.wangsulist[res.tapIndex]
					},
					fail: function(res) {
						console.log(res.errMsg);
					}
				});
			},
			selectquyu: function() {
				uni.showActionSheet({
					itemList: that.quyulist,
					itemColor: '#838383',
					success: function(res) {
						that.diyu = that.quyulist[res.tapIndex]
					},
					fail: function(res) {
						console.log(res.errMsg);
					}
				});
			},

			lijizhuce: function() {
				if (!that.strname) {
					uni.showToast({
						title: '请输入姓名'
					})

					return
				}
				if (!that.zhanghao) {
					uni.showToast({
						title: '请输入账号'
					})

					return
				}
				if (!that.yanzhengmacode) {
					uni.showToast({
						title: '请输入验证码'
					})

					return
				}
				if (!that.xuehao) {
					uni.showToast({
						title: '请输入学号'
					})

					return
				}
				if (!that.zhengjianhaoma) {
					uni.showToast({
						title: '请输入证件号码'
					})

					return
				}
				if (!that.diyu) {
					uni.showToast({
						title: '请输入所在地域'
					})

					return
				}
				if (!that.mima) {
					uni.showToast({
						title: '请输入登陆密码'
					})

					return
				}
				if (!that.mima) {
					uni.showToast({
						title: '请输入登陆密码'
					})

					return
				}
				if (that.wangshuliang == 0) {
					uni.showToast({
						title: '请输入数量'
					})

					return
				}
				if (that.iptvshuliang == 0) {
					uni.showToast({
						title: '请输入数量'
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
