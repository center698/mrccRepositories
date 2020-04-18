<template>
	<view class="content">
		<view class="timeli">2020.02.02</view>
		<view
			class="uni-swiper-msg"
			style="padding-left: 30rpx; padding-right: 30rpx; background-color: #FFFFFF; margin-top: 10rpx; margin-bottom: 10rpx;"
			v-for="(item, index) in msg"
			:key="index"
		>
			<view class="uni-swiper-msg-icon"><image src="../../static/tongzhiico.png" mode="widthFix"></image></view>
			<navigator @click="gonggao(index)" style="overflow: hidden;text-overflow:ellipsis;white-space: nowrap; width: 80%;">{{ item }}</navigator>
		</view>
		<view class="timeli">2020.02.02</view>
		<view
			class="uni-swiper-msg"
			style="padding-left: 30rpx; padding-right: 30rpx; background-color: #FFFFFF; margin-top: 10rpx; margin-bottom: 10rpx;"
			v-for="(item, index) in msg"
			:key="index"
		>
			<view class="uni-swiper-msg-icon"><image src="../../static/tongzhiico.png" mode="widthFix"></image></view>
			<navigator @click="gonggao(index)" style="overflow: hidden;text-overflow:ellipsis;white-space: nowrap; width: 80%;">{{ item }}</navigator>
		</view>
	</view>
</template>

<script>
var that;
export default {
	data() {
		return {
			msg: [
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发带我去服务器负担物权法的武器发带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发',
				'带我去服务器负担物权法的武器发'
			]
		};
	},
	onLoad: function(e) {
		that = this;
	},
	onShow: function(res) {},
	methods: {
		gonggao:function(e){
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
				url: './news_detail?detailDate=' + encodeURIComponent(JSON.stringify(detail))
			});
		}
	}
};
</script>

<style lang="scss">
page {
	background-color: #f7f7f7;
}

.content {
	display: flex;
	flex-direction: column;
	width: 100%;
}
.timeli {
	width: 100%;
	height: 36px;
	line-height: 36px;
	text-align: center;
	&::before {
		content: '';
		display: inline-block;
		width: 80rpx;
		border-top: 2rpx solid #cccccc;
		vertical-align: 10rpx;
	}
	&::after {
		content: '';
		display: inline-block;
		width: 80rpx;
		border-top: 2rpx solid #cccccc;
		vertical-align: 10rpx;
	}
	
}
</style>
