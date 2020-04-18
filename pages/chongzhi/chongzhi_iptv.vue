<template>
	<view class="content">
		<view style="width: 100%; padding: 50upx 0upx; color: #333333; font-weight: 700; font-size: 43upx; text-align: center;">IPTV充值</view>
		<view style="width: 72%; height: 70upx; margin-left: 10%; display: flex; flex-direction: row; margin: 20rpx auto;">
			<view style="flex: 2; height: 70upx;  line-height: 70upx; color: #333333; font-weight: 700; font-size: 34rpx; margin-right: 20upx;">充值账户</view>
			<view style="flex: 5; height: 70upx;  line-height: 70upx; color: #333333; font-size: 32rpx; margin-right: 20rpx; overflow: hidden;border: 1rpx solid #D9D9D9; padding: 0 20rpx; border-radius: 100rpx; " @tap="seluser">{{user}}</view>
			<!-- <input style="flex: 1; height: 70upx; line-height: 70upx;"></input> -->
		</view>
		<view class="selmon">
			<button :class="{ selected: selm[0] }" type="default" @tap="selms(0)">1个月</button>
			<button :class="{ selected: selm[1] }" type="default" @tap="selms(1)">2个月</button>
			<button :class="{ selected: selm[2] }" type="default" @tap="selms(2)">3个月</button>
		</view>
		<view class="selyear">
			<button :class="{ selected: selm[3] }" type="default" @tap="selms(3)">半年</button>
			<button :class="{ selected: selm[4] }" type="default" @tap="selms(4)">一年</button>
		</view>
		
		<view class="subbtn">
			<button type="default">立即充值</button>
		</view>
		
	</view>
</template>

<script>
	var that;
	export default {
		data() {
			return {
				selm:[false,false,false,false,false],
				user:"760495276@163.com",
				itemList: ['123456789@163.com', '987654654@163.com', '444586992@163.com']
			}
		},
		onLoad: function(e) {
			that = this;
		},
		onShow: function(res) {
			
		},
		methods: {
			selms:function(e){
				that.selmrefresh();
				that.selm[e]=true;
				console.log(e);
			},
			selmrefresh:function(){
				that.selm=[false,false,false,false,false];
			},
			seluser:function(e){
				uni.showActionSheet({
				    itemList: that.itemList,
				    success: function (res) {
						that.user=that.itemList[res.tapIndex];
				        console.log('选中了第' + (res.tapIndex + 1) + '个按钮');
				    },
				    fail: function (res) {
				        console.log(res.errMsg);
				    }
				});
			}
		}

	}
</script>

<style lang="scss">
	page {
		background-color: #F7F7F7;
	}

	.content {
		display: flex;
		flex-direction: column;
		width: 100%;
	}
	.selmon{
		display: flex; 
		flex-direction: row; 
		width: 70%;
		margin: 20rpx auto; 
		color: #007AFF;
		flex: 1;
		button{
			color: #007AFF;
			border-radius: 100rpx; 
			border: 1rpx solid #E0E0E0;
			text-align: center;
			padding-left: 36rpx;
			padding-right: 36rpx;
			box-shadow: 2rpx 3rpx 10rpx 3rpx #EEEEEE;
		}
		button::after{
			display: none;
		}
	}
	.selyear{
		display: flex;
		flex-direction: row; 
		width: 56%;
		margin: 20rpx auto; 
		color: #007AFF;
		flex: 1;
		button{
			color: #007AFF;
			border-radius: 100rpx; 
			border: 1rpx solid #E0E0E0;
			text-align: center;
			padding-left: 56rpx;
			padding-right: 56rpx;
			box-shadow: 2rpx 3rpx 10rpx 3rpx #EEEEEE;
		}
		button::after{
			display: none;
		}
	}
	.subbtn{
		display: flex;
		flex-direction: row; 
		width: 56%;
		margin: 20rpx auto;
		margin-top: 200rpx;
		color: #007AFF;
		flex: 1;
		button{
			color: #FFFFFF;
			background-color: #007AFF;
			border-radius: 100rpx; 
			border: 1rpx solid #E0E0E0;
			text-align: center;
			padding-left: 56rpx;
			padding-right: 56rpx;
			box-shadow: 2rpx 3rpx 10rpx 3rpx #EEEEEE;
		}
		button::after{
			display: none;
		}
	}
	.content .selected{
		color: #FFFFFF;
		background-color: #007AFF;
		border: 1rpx solid #007AFF;
	}
	
</style>
