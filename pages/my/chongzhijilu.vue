<template>
	<view class="content">
		<view style="width: 100%; height: 90upx; display: flex; flex-direction: row; background-color: #FFFFFF;">
			<view style="flex: 1; height: 90upx; line-height: 90upx; text-align: center; color: #555555; font-size: 28upx;">时间</view>
			<view style="width: 2upx; height: 30upx; margin-top: 30upx; background-color: #9c9c9c;"></view>
			<view style="flex: 1; height: 90upx; line-height: 90upx; text-align: center; color: #555555; font-size: 28upx;">账号</view>
			<view style="width: 2upx; height: 30upx; margin-top: 30upx; background-color: #9c9c9c;"></view>
			<view style="flex: 1; height: 90upx; line-height: 90upx; text-align: center; color: #555555; font-size: 28upx;">套餐类型</view>
			<view style="width: 2upx; height: 30upx; margin-top: 30upx; background-color: #9c9c9c;"></view>
			<view style="flex: 1; height: 90upx; line-height: 90upx; text-align: center; color: #555555; font-size: 28upx;">金额</view>
		</view>

		<block v-for="(item,num) in lists" :key="num">
			<view style="width: 100%; height: 80upx; display: flex; flex-direction: row; background-color: #FFFFFF; margin-top: 10upx;">
				<view style="flex: 1; height: 80upx; line-height: 80upx; text-align: center; color: #888888; font-size: 24upx;">{{item.shijian}}</view>
				<view style="flex: 1; height: 80upx; line-height: 80upx; text-align: center; color: #888888; font-size: 24upx;">{{item.zhanghao}}</view>
				<view style="flex: 1; height: 80upx; line-height: 80upx; text-align: center; color: #888888; font-size: 24upx;">{{item.taocan}}</view>
				<view style="flex: 1; height: 80upx; line-height: 80upx; text-align: center; color: #888888; font-size: 24upx;">{{item.jine}}</view>
			</view>
		</block>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				lists: [{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '一个月',
						jine: '100元'
					},
					{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '两个月',
						jine: '200元'
					},
					{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '三个月',
						jine: '300元'
					},
					{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '半年',
						jine: '600元'
					},
					{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '一年',
						jine: '1000元'
					},
					{
						shijian: '03.23 23:24',
						zhanghao: '18191217921',
						taocan: '两年',
						jine: '1500元'
					},
				]
			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {

		},
		methods: {

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
