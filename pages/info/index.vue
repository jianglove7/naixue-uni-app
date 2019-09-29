<template>
	<view class="app-container">
		<scroll-view class="content" scroll-y="true">
			<view class="wrap header" style="background-position: 0% 0%; background-size: 100% 100%; background-repeat: no-repeat; background-image:url(../../static/images/bg.jpg);">
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
			<view class="wrap func-list">
				<view class="hd">
					<view class="pre"></view>
					<text class="hd-tit">我的服务</text>
				</view>
				<view class="list">
					<view v-for="(item,index) in systemFuncList" :key="index" class="item">
						<image :src="item.img" class="image"></image>
						<view><text class="text">{{item.name}}</text></view>
					</view>
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
			console.log(systemFuncList)
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
		height: 100%;
		background-color: #f7f7f7;
	}
	.wrap{
		overflow: hidden;
		background-color: #fff;
		margin-left: 10rpx;
		margin-right: 10rpx;
		margin-bottom: 10rpx;
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
	
	.func-list{
		.hd{
			display: flex;
			flex-direction: row;
			justify-content: flex-start;
			padding: 50rpx 20rpx;
			.pre{
				width: 10rpx;
				height: 24rpx;
				background-color: $main-color;
				margin-right: 20rpx;
			}
			.hd-tit{
				font-size: 26rpx;
			}
		}
		
		.list{
			display: flex;
			flex-direction:row;
			justify-content: flex-start;
			flex-wrap:wrap;
			align-items:flex-start;
			.item{
				display: flex;                                                                                        
				flex-direction: column;
				align-items: center;
				width: 25%;
				margin-bottom: 80rpx;
				.image{
					width: 60rpx;
					height: 60rpx;
					margin-bottom: 30rpx;
				}
				.text{
					font-size: 28rpx;
				}
			}
		}
	}
	
	
</style>
