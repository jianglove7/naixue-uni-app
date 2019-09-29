<template>
    <view class="nx-slider">
        <swiper class="carousel" circular @change="swiperChange" :current="bannerIndex">
        	<swiper-item v-for="(item, index) in imageList" :key="index" class="carousel-item">
        		<image class="image" :src="item.src" />
        	</swiper-item>
        </swiper>
        <!-- 自定义swiper指示器 -->
        <view class="swiper-dots">
			<view  v-for="(item, index) in imageList" :key="index" :class="['dot-item',bannerIndex===index?'dot-active':'']"></view>
        </view>
    </view>
</template>

<script>
export default {
  props: ['imageList'],
  data () {
    return {
		bannerIndex:0
    }
  },
  
  methods: {
    //轮播图切换修改背景色
    swiperChange(e) {
    	const index = e.detail.current;
    	this.bannerIndex = index;
    	// this.titleNViewBackground = this.carouselList[index].background;
    },
  }
}
</script>

<style scoped>
    .nx-slider {
        width: 100%;
		height: 300rpx;
		position: relative;
    }
    .image {
        width: 100%;
        height: 300rpx;
		overflow: hidden;
    }
    .swiper-dots {
		display: flex;
		justify-content: center;
        width: 100%;
        height: 20rpx;
        position: absolute;
        bottom: 10rpx;
		left: 0;
        right: 0;
    }
	.dot-item{
		margin: 0 5rpx;
		width: 20rpx;
		height: 20rpx;
		border-radius: 50%;
		background-color: #fff;
	}
	.dot-active{
		background-color: #cca33a;
	}
</style>
