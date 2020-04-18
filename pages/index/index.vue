<template>
	<view class="content">
		<view class="uni-swiper-msg" style="padding-left: 30rpx; padding-right: 30rpx; background-color: #FFFFFF; margin-top: 10rpx; margin-bottom: 10rpx;">
			<view class="uni-swiper-msg-icon">
				<image src="../../static/tongzhiico.png" mode="widthFix"></image>
			</view>
			<swiper vertical="true" autoplay="true" circular="true" interval="5000">
				<swiper-item v-for="(item, index) in msg" :key="index">
					<text @tap="gonggao(index)">{{item}}</text>
				</swiper-item>
			</swiper>
		</view>
		
		
		<swiper style="width: 100%; height: 350rpx; " autoplay="true" circular="true" indicator-dots="true" indicator-color="#ffffff"
		 indicator-active-color="#1dadff" interval="3000">
			<block v-for="(item, index) in imgs" :key="index">
				<swiper-item>
					<image style="width: 100%; height: 350rpx; " :src="item" mode="widthFix" @click="lunbotu(index)"></image>
				</swiper-item>
			</block>
		</swiper>
		<view style="flex: 1; background-color: #FFFFFF; display: flex; flex-direction: row; padding: 40rpx; margin-top: 50rpx;">
			<image style="flex: 1;" mode="widthFix" src="https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/16/5e1122e669e50ce338431624a5a13589.png" @click="wangfeichongzhi"></image>
			<view style="width: 30rpx; height: 1rpx;"></view>
			<image style="flex: 1;" mode="widthFix" src="https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/16/c2592f9f77860b1790d75a00c243090e.png" @click="iptvchongzhi"></image>

		</view>
		<view style="flex: 1;background-color: #FFFFFF; display: flex; flex-direction: row; padding: 0rpx 40rpx 50rpx 40rpx;">
			<image style="flex: 1;" mode="widthFix" src="https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/16/2ab516ca132bc77112d57ef2b965c8ce.png" @click="xinwenzixun"></image>
			<view style="width: 30rpx; height: 1rpx;"></view>
			<image style="flex: 1;" mode="widthFix" src="https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/16/d95b45aa73095fd3bdd972566705d2cd.png" @click="lishitongzhi"></image>

		</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				title: 'Hello',
				msg: [
					'uni-app行业峰会频频亮相，开发者反响热烈',
					'DCloud完成B2轮融资，uni-app震撼发布',
					'36氪热文榜推荐、CSDN公号推荐 DCloud CEO文章'
				],
				imgs: [
					'https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/16/4d9aa70d07bae8554c819d43e9593839.png',
					'https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/03/19/753d0892ab950ebf02fb86becc67bcd5.png'
				]
			}
		},
		onLoad() {
			that = this;

		},
		methods: {
			gonggao: function(pos){
				let detail = {
					author_name: "未来汽车日报",
					content: "",
					cover: "https://img.36krcdn.com/20200410/v2_9c3331af67e64994aa97a27fffb1a380_img_png?x-oss-process=image/resize,m_mfit,w_520,h_300/crop,w_520,h_300,g_center",
					id: 121375,
					post_id: "5310910",
					published_at: "2020-04-11 17:07:48",
					title: "为什么自动驾驶诉讼不断？"
				};
				uni.navigateTo({
					url: '../news/news_detail?detailDate=' + encodeURIComponent(JSON.stringify(detail))
				});
				return;
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
			},
			lunbotu: function(pos){
				let detail = {
					author_name: "未来汽车日报",
					content: "",
					cover: "https://img.36krcdn.com/20200410/v2_9c3331af67e64994aa97a27fffb1a380_img_png?x-oss-process=image/resize,m_mfit,w_520,h_300/crop,w_520,h_300,g_center",
					id: 121375,
					post_id: "5310910",
					published_at: "2020-04-11 17:07:48",
					title: "为什么自动驾驶诉讼不断？"
				};
				uni.navigateTo({
					url: '../news/news_detail?detailDate=' + encodeURIComponent(JSON.stringify(detail))
				});
				return;
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
			},
			wangfeichongzhi: function(pos){
				uni.navigateTo({
					url:"../chongzhi/chongzhi_wangfei"
				})
				return;
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
			},
			iptvchongzhi: function(pos){
				uni.navigateTo({
					url:"../chongzhi/chongzhi_iptv"
				})
				return;
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
			},
			xinwenzixun: function(pos){
				uni.navigateTo({
					url:"../news/news_list"
				})
				return;
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
			},
			lishitongzhi: function(pos){
				
				uni.navigateTo({
					url:"../news/msg_list"
				})
				return;
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
			}
		}
	}
</script>

<style>
	page {
		background-color: #f1f1f1;
	}

	.content {
		display: flex;
		flex-direction: column;
		width: 100%;
	}
</style>
