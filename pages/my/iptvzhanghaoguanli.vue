<template>
	<view class="content">
		<view style="width: 98%; height: 280upx; position: relative; margin-left: 1%;">
			<image style="width: 100%; height: 280upx; " :src="strurl3" mode="aspectFit"></image>
			<view style="width: 100%; color: #FFFFFF; font-weight: 700; font-size: 30upx; margin-top: 20upx; margin-left: 20upx; position: absolute; top: 0upx; display: flex; flex-direction: row;">
				<view style=" color: #FFFFFF; font-weight: 700; font-size: 30upx; margin-top: 20upx; margin-left: 7upx; margin-right: 20upx;">01</view>
				<view style="flex: 2; display: flex; flex-direction: column; heihht: 280upx; padding-top: 40upx;padding-left: 10upx; padding-right: 20upx;">
					<view style="width: 100%; height: 70upx; line-height: 70upx; font-size: 30upx; color: #FFFFFF; font-weight: 700;">123456789000</view>
					<view style="width: 100%; height: 50upx; line-height: 50upx; font-size: 18upx; color: #FFFFFF; ">初始时间：2020.01.01
						剩余时间：12小时59分</view>
					<view style="width: 100%; height: 30upx; line-height: 30upx; font-size: 22upx; color: #FFFFFF; font-weight: 700;">套餐类型：
						100M</view>
					<view style="width: 100%; height: 50upx; display: flex; flex-direction: row;">
						<view style="flex: 1; height: 50upx;"></view>
						<view style="width: 100upx; height: 40upx; line-height: 40upx; border: 2upx solid #FFFFFF; border-radius: 50rpx; color: #FFFFFF; font-size: 22upx; text-align: center; margin-right: 20upx;" @click="chongzhi">充值</view>
					</view>
				</view>
				<view style="flex: 1; display: flex; flex-direction: column; heihht: 280upx;  margin-top: 40upx; ">
					<view style="width: 100%; height: 30upx; display: flex; flex-direction: row; align-items: center;">
						<image src="../../static/zhengchangico.png" style="width: 15upx; height: 15upx;"></image>
						<view style=" height: 50upx; line-height: 50upx;  color: #FFFFFF; font-size: 23upx; text-align: center; margin-left: 10upx;">正常</view>
					</view>
					<view style="width: 100%; height: 120upx;"></view>
					<view style="width: 140upx; height: 40upx; line-height: 40upx; border: 2upx solid #FFFFFF; border-radius: 50upx; color: #FFFFFF; font-size: 22upx; text-align: center;" @click="xiugaimima">修改密码</view>
				</view>
			</view>
		</view>
		
		
		<view style="width: 98%; height: 280upx; position: relative; margin-left: 1%; ">
			<image style="width: 100%; height: 280upx; " :src="strurl2" mode="aspectFit"></image>
			<view style="width: 100%; color: #FFFFFF; font-weight: 700; font-size: 30upx; margin-top: 20upx; margin-left: 20upx; position: absolute; top: 0upx; display: flex; flex-direction: row;">
				<view style=" color: #FFFFFF; font-weight: 700; font-size: 30upx; margin-top: 20upx; margin-left: 7upx; margin-right: 20upx;">02</view>
				<view style="flex: 2; display: flex; flex-direction: column; heihht: 280upx; padding-top: 40upx;padding-left: 10upx; padding-right: 20upx;">
					<view style="width: 100%; height: 70upx; line-height: 70upx; font-size: 30upx; color: #FFFFFF; font-weight: 700;">123456789000</view>
					<view style="width: 100%; height: 50upx; line-height: 50upx; font-size: 18upx; color: #FFFFFF; ">初始时间：2020.01.01
						剩余时间：12小时59分</view>
					<view style="width: 100%; height: 30upx; line-height: 30upx; font-size: 22upx; color: #FFFFFF; font-weight: 700;">套餐类型：
						100M</view>
					<view style="width: 100%; height: 50upx; display: flex; flex-direction: row;">
						<view style="flex: 1; height: 50upx;"></view>
						<view style="width: 100upx; height: 40upx; line-height: 40upx; border: 2upx solid #FFFFFF; border-radius: 50rpx; color: #FFFFFF; font-size: 22upx; text-align: center; margin-right: 20upx;" @click="chongzhi">充值</view>
					</view>
				</view>
				<view style="flex: 1; display: flex; flex-direction: column; heihht: 280upx;  margin-top: 40upx; ">
					<view style="width: 100%; height: 30upx; display: flex; flex-direction: row; align-items: center;">
						<image src="../../static/yichangico.png" style="width: 15upx; height: 15upx;"></image>
						<view style=" height: 50upx; line-height: 50upx;  color: #FFFFFF; font-size: 23upx; text-align: center; margin-left: 10upx;">异常</view>
					</view>
					<view style="width: 100%; height: 120upx;"></view>
					<view style="width: 140upx; height: 40upx; line-height: 40upx; border: 2upx solid #FFFFFF; border-radius: 50upx; color: #FFFFFF; font-size: 22upx; text-align: center;" @click="xiugaimima">修改密码</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				strurl1: 'https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/17/8706707f445b24172a4949e7753ee5e5.png',
				strurl2: 'https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/17/2d94099853bf30038bd3ccae01715a8d.png',
				strurl3: 'https://zzwl1zsxn.oss-cn-hangzhou.aliyuncs.com/images/2020/04/17/df6401be3dc8b59ea6aea90d8c730b80.png'
			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {

		},
		methods: {
			chongzhi:function(){
				uni.navigateTo({
					url:'../chongzhi/chongzhi_iptv'
				})
			},
			xiugaimima:function(){
				uni.showToast({
					title:'修改成功'
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
