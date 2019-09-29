<template>
	<view class="app-header">
	<!-- 标题栏和状态栏占位符 -->
		<view class="titleNview-placing"></view>
		<view :class="['wrapper'] "><!-- , isIpx&&isIpx()?'w-ipx':'' -->
			<view class="left" @click="goSelectStore">
	        <text class="left-title">广州番禺万达广场店 ></text>
	        <view class="flex-row">
	           <image class="left-icon" src="../../static/images/local.jpg"></image>
	           <text class="left-text">距离您5.2km</text>
	        </view>
	
	      </view>
	      <view class="right">
	        <view class="btn-group">
	          <text :class="['btn-item',!isTakeOut?'btn-active':'']" @click="changeType(false)">自取</text>
	          <text :class="['btn-item',isTakeOut?'btn-active':'']" @click="changeType(true)">外卖</text>
	        </view>
	      </view>
	  </view>
		<image src="../../static/images/shadow.jpg" class="head-shadow"></image>
	</view>
</template>
	
<script>
	export default {
		data () {
		  return {
		    isTakeOut: false
		  }
		},
		methods: {
		  changeType (isTakeOut) {
		    this.isTakeOut = isTakeOut
		  },
		  goSelectStore () {
		    this.jump('/selectStore')
		  }
		}
	}
</script>

<style lang="scss" scoped>
	.app-header{
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		
		.wrapper {
			display: flex;
			width: 100%;
		    flex-direction: row;
			align-items: center;;
		    justify-content:space-between;
		    border-top-color: #a0a0a0;
		    background-color: #ffffff;
		    padding:10rpx 20rpx;
		}
		.head-shadow{
		  width: 100%;
		  height: 20rpx;
		}
		
		.left-title{
		  font-size: 32rpx;
		  line-height: 32rpx;
		}
		
		.flex-row{
			display: flex;
			margin-top: 10rpx;
			line-height:1.4;
		}
		.left-icon{
		  width:24rpx;
		  height:24rpx;
		  margin-right: 10rpx;
		}
		
		.left-text{
		  color:#a0a0a0;
		  display: inline-block;
		  // line-height: .6rem;
		  font-size: 22rpx;
		}
		
		.btn-group{
			
		  display: flex;
		  flex-direction: row;
		  justify-content: center;
		  align-items: center;
		  overflow: hidden;
		  width:160rpx;
		  height:56rpx;
		  line-height: 56rpx;
		  text-align: center;
		  border-style:solid;
		  border-width:1rpx;
		  border-radius: 80rpx;
		  border-color:#a0a0a0;
		  padding-left:2rpx;
		  padding-right: 2rpx;
		
		}
		.btn-item{
		  display: inline-block;
		  height:48rpx;
		  line-height:48rpx;
		  border-radius: 24rpx;
		  font-size:24rpx;
		  text-align: center;
		  flex: 1;
		  color:#a0a0a0;
		  overflow: hidden;
		}
		.btn-active{
		  background-color: #cca33a;
		  border-radius: 24rpx;
		  color: #fff;
		}
	}
	
	
</style>
