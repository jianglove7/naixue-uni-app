<template>
	<view class="app-container">
		
		<scroll-view class="content" scroll-y="true">
			<view class="header">
				<view class="left">
					<text class="hd-text">广州</text>
					<text  v-if="!showSelectForm" class="hd-text">番禺</text>
					<IconFont class="icon" icon="iconicon-test7"></IconFont>
				</view>
				<view class="right">
					<view class="form" v-if="showSelectForm">
						<view class="wrap">
							<IconFont class="icon" icon="iconicon-test"></IconFont>
							<input class="input" type="text" :value="selectText"/>
						</view>
						<text class="cancel">取消</text>
					</view>
					<view class="view" v-if="!showSelectForm" @click="toggleSelectForm">
						<view class="wrap">
							
							<!-- <input type="text" :value="selectText" /> -->
							<IconFont class="icon" icon="iconicon-test"></IconFont>
							<text class="text">搜索</text>
						</view>
						
					</view>
					
				</view>
			</view>
			<!-- 地图 -->
			<view class="ditu">
				<text>地图</text>
			</view>
			<!-- 地图 end -->
			<!-- 店铺列表 -->
			<view class="store-list">
				<view class="item">
					<view class="left">
						<view class="hd">
							<text class="text">广州番禺万达广场店</text>
							<text>营业中</text>
						</view>
						<view class="near">
							<text class="text">距离您5.2km</text>
						</view>
						<view  class="addr">
							<text class="text">广州市番禺区南村镇兴南大道368号万博中心123号</text>
						</view>
						<view class="time">
							<text class="text">营业时间：10:00-22:00</text>
						</view>
					</view>
					<view class="right flex-column">
						<view  class="hd">
							<text class="text">去下单 ></text>
						</view>
						<view class="bd">
							<IconFont class="icon" icon="icontelephone"></IconFont>
							<text class="text">|</text>
							<IconFont class="icon" icon="iconcourse"></IconFont>
						</view>
					</view>
				</view>
			</view>
			<!-- 店铺列表 -->
        </scroll-view>
	</view>
</template>

<script lang="ts">
    import Vue from 'vue';
	import IconFont from '@/components/IconFont.vue'
	export default Vue.extend({
		components:{
			IconFont,
		},
		data() {
			return {
				selectText:'',
				showSelectForm:true
			}
		},
		onLoad() {

		},
		methods: {
			toggleSelectForm(){
				this.showSelectForm=!this.showSelectForm
			}
		}
	});
</script>

<style lang="scss" scoped>

	.app-container{
		position: fixed;
		background-color: #f7f7f7;
		top: 0;
		bottom:var(--window-bottom);
		left: 0;
		right: 0;
		margin-top: var(--status-bar-height);
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
	}
	.content{
		width: 100%;
		
	}
	
	.header{
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 10rpx 40rpx;
		background-color: #fff;
		.left{
			display: flex;
			flex-direction: row;
			line-height: 32rpx;
			align-items: center;
			.icon{
				font-size:50rpx;
			}
		}
		.hd-text{
			margin-right: 10rpx;
			font-size: 32rpx;
			// font-weight: bold;
		}
		
		.right{
			flex: 1;
			display: flex;
			flex-direction: row;
			align-items: center;
			line-height: 32rpx;
			.form{
				width: 100%;
				display: flex;
				justify-content: space-between;
				align-items: center;
				.wrap{
					flex: 1;
					display: flex;
					justify-content: space-between;
					align-items: center;
					border-width:1rpx ;
					border-color: #999999;
					border-style: solid;
					border-radius: 30rpx;
					height: 60rpx;
					padding: 0 20rpx;
					.input{
						flex:1;
						font-size: 24rpx;
						color: #999;
						line-height:24rpx;
					}
					.icon{
						color: #999;
						font-size: 36rpx;
						margin-right: 10rpx;
					}
					
				}
				.cancel{
					margin-left: 20rpx;
					color: #999;
					font-size: 30rpx;
				}
			}
			.view{
				.wrap{
					width: 150rpx;
					height: 70rpx;
					background-color: #f7f7f7;
					border-radius: 35rpx;
					text-align: center;
					display: flex;
					flex-direction: row;
					padding: 0 25rpx;
					align-items: center;
					justify-content: space-between;
					.icon{
						color: #999;
						font-size: 36rpx;
					}
					.text{
						font-size: 28rpx;
						color: #999;
					}
					
				}
			}
			.form{
				
			}
			.icon{
				font-size:50rpx;
			}
		}
	}
	
	.ditu{
		height:400rpx;
		background-color: #fff;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	
	.store-list{
		.item{
			background-color: #fff;
			display: flex;
			justify-content: space-between;
			margin: 20rpx;
			padding: 20rpx;
			.hd{
				.text{
					font-size: 32rpx;
				}
			}
			.near{
				.text{
					font-size: 24rpx;
				}
			}
			.addr{
				overflow: hidden;
				text-overflow:ellipsis;
				white-space: nowrap;
				.text{
					font-size:24rpx;
					color: #999999;
				}
			}
			.time{
				.text{
					font-size:24rpx;
					color: #999999;
				}
			}
			
			.right{
				margin-left: 30rpx;
				width: 300rpx;
			}
		}
	}
	
	
</style>
