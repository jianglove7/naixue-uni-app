<template>
	<view class="app-container">
		<scroll-view class="content" scroll-y="true">
			<view class="wrap header">
				<view class="hd">
					<image class="user-img" src="../../static/images/avast.jpg"></image>
					<view class="user-name-wrap">
						<text class="user-name">豪</text>
					</view>
					<view class="btn-list">
						<view class="item">
							<view class="hd"><text class="tit">1</text></view>
							<view class="bd"><text class="sub">奈雪劵</text></view>
						</view>
						<view class="item">
							<view class="hd"><text class="tit">106</text></view>
							<view class="bd"><text class="sub">积分商城</text></view>
						</view>
						<view class="item">
							<view class="hd"><text class="tit">0</text></view>
							<view class="bd"><text class="sub">礼品劵</text></view>
						</view>
					</view>
					<view class="qrcode-wrap">
						<IconFont class="qrcode" icon="iconscan"></IconFont>
						<text  class="text">会员码</text>
					</view>
				</view>
				
			</view>
			<view class="wrap">
				<view class="list">
					<view class="item"></view>
				</view>
			</view>
        </scroll-view>
	</view>
</template>

<script>
	import IconFont from '@/components/IconFont.vue'
	import {systemFuncList} from '@/json.js'
    import Vue from 'vue';
	export default Vue.extend({
		components:{
			IconFont
		},
		data() {
			return {
				systemFuncList:[]
			}
		},
		onLoad() {

		},
		created(){
			this.systemFuncList = systemFuncList
		},
		methods: {

		}
	});
</script>

<style lang="scss" scoped>
	.app-container{
		position: fixed;
		background-color: #fff;
		top: 0;
		bottom:var(--window-bottom);
		left: 0;
		right: 0;
		margin-top: var(--status-bar-height);
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.content{
		flex: 1;
		background-color: #f7f7f7;
	}
	.wrap{
		background-color: #fff;
		margin: 10rpx;
	}
	
	.hd{
		position: relative;
		padding: 10rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
		
		.user-img{
			width: 130rpx;
			height: 130rpx;
			border-radius: 65rpx;
			margin-bottom: 20rpx;
		}
		.user-name-wrap{
			margin-bottom: 100rpx;	
			line-height: 32rpx;
		}
		.user-name{
			font-size: 32rpx;
		}
		
		.btn-list{
			display: flex;
			width: 100%;
			justify-content: space-around;
			margin-bottom: 60rpx;
			.item{
				.hd{
					line-height: 50rpx;
				}
				.bd{
					line-height: 30rpx;
				}
				.tit{
					font-size: 50rpx;
				}
				.sub{
					font-size: 30rpx;
				}
			}
		}
		
	}

	.qrcode-wrap{
		position: absolute;
		right: 40rpx;
		top:50rpx;
		text-align: center;
		
		.qrcode{
			font-size: 60rpx;
		}
		.text{
			font-size: 24rpx;
		}
	}
	
	
</style>
