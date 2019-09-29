<template>
	<view class="app-container">
		<!-- <view class="titleNview-placing"></
		
		view> -->
		<view class="content">
			<image class="img" src="../../static/images/empty.jpg"></image>
			<view class="row">
				<text class="text">您还没有点单，</text>
			</view>
			<view class="row">
				<text class="text">快去犒劳一下自己吧~</text>
			</view>
			<button class="btn">去点单</button>
			
			<view class="row">
				<text class="text grey">历史订单 ></text>
			</view>
        </view>
	</view>
</template>

<script lang="ts">
    import Vue from 'vue';
	export default Vue.extend({
		data() {
			return {
			}
		},
		onLoad() {

		},
		methods: {

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
		justify-content: center;
		align-items: center;
	}
	
	.content{
		
		
	}
	
	.row{
		text-align: center;
	}
	.text{
		font-size: 24rpx;
	}
	.btn{
		margin-top: 100rpx;
		width: 300rpx;
		height: 80rpx;
		font-size: 24rpx;
		line-height: 80rpx;
		background-color: #ae8a32;
		color: #fff;
		border-radius: 0;
		margin-bottom: 30rpx;
	}
	.grey{
		color: grey;
	}
	
	.img{
		width: 350rpx;
		height: 350rpx;
	}
</style>
