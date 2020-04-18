<template>
	<view class="content">
		<view style="width: 100%; padding: 50upx 0upx; color: #333333; font-weight: 700; font-size: 33upx; text-align: center;">用户信息管理</view>
		<view style="width: 80%; height: 70upx; margin-left: 10%; display: flex; flex-direction: row; margin-top: 20upx;">
			<view style="height: 70upx;  line-height: 70upx; color: #333333; font-size: 28upx; margin-right: 20upx;">姓名</view>
			<input style="flex: 1; height: 70upx; line-height: 70upx; margin-left: 20upx; margin-right: 20upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="text" placeholder="请输入你的姓名" confirm-type="done" v-model="zhanghao"></input>
		</view>
		<view style="width: 80%; height: 70upx; margin-left: 10%; display: flex; flex-direction: row; margin-top: 20upx;">
			<view style="height: 70upx;  line-height: 70upx; color: #333333; font-size: 28upx; margin-right: 20upx;">学号</view>
			<input style="flex: 1; height: 70upx; line-height: 70upx; margin-left: 20upx; margin-right: 20upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="text" placeholder="请输入你的学号" confirm-type="done" v-model="xuehao"></input>
		</view>
		<view style="width: 80%; height: 70upx; margin-left: 10%; display: flex; flex-direction: row; margin-top: 20upx;">
			<view style="height: 70upx;  line-height: 70upx; color: #333333; font-size: 28upx; margin-right: 20upx;">证件号码</view>
			<input style="flex: 1; height: 70upx; line-height: 70upx; margin-left: 20upx; margin-right: 20upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="text" placeholder="请输入证件号码" confirm-type="done" v-model="zhengjianhaoma"></input>
		</view>
		<view style="width: 80%; height: 70upx; margin-left: 10%; display: flex; flex-direction: row; margin-top: 20upx;" @click="selectquyu">
			<view style="height: 70upx;  line-height: 70upx; color: #333333; font-size: 28upx; margin-right: 20upx;">所在区域</view>
			<input style="flex: 1; height: 70upx; line-height: 70upx; margin-left: 20upx; margin-right: 20upx; text-align: left; padding-left: 50upx; padding-right: 50upx; font-size: 28upx; color: #555555; border: 1upx solid #ececec; border-radius: 50upx; background-color: #FFFFFF;"
			 type="text" placeholder="请选择所在区域" confirm-type="done" v-model="suozaiquyu" disabled="true"></input>
		</view>
		<view style="border-radius: 50upx;width: 60%; margin-left: 20%; height: 70upx; line-height: 70upx; text-align: center; background-color: #1d89ff; color: #FFFFFF; font-size: 30upx; margin-top: 100upx;"
		 @click="lijidenglu">确认保存</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				zhanghao: '',
				xuehao: '',
				zhengjianhaoma: '',
				suozaiquyu: '',
				quyulist: ['西安交通大学', '西北工业大学', '西安音乐学院'],
			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {

		},
		methods: {
			selectquyu: function() {
				uni.showActionSheet({
					itemList: that.quyulist,
					itemColor: '#838383',
					success: function(res) {
						that.suozaiquyu = that.quyulist[res.tapIndex]
					},
					fail: function(res) {
						console.log(res.errMsg);
					}
				});
			},
			lijidenglu: function() {
				if (!that.zhanghao) {
					uni.showToast({
						title: '请输入账号'
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
				if (!that.suozaiquyu) {
					uni.showToast({
						title: '请选择所在区域'
					})

					return
				}
				uni.navigateBack({
					delta: 1
				})

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
</style>
