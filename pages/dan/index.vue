<template>
	<view class="app-container">
		<view class="titleNview-placing"></view>
		<MainHeader></MainHeader>
		<view class="app-content flex-row">
			<scroll-view class="left menu-list" scroll-y="true">
				  <view  v-for="(item,index) in categoryList" :key="index" :class="['menu-item',item.id===curCategory?'menu-active':'']">
				    <text class="menu-text">{{item.name}}</text>
				  </view>
			</scroll-view>
			<scroll-view class="right" scroll-y="true">
				<NxSlider :imageList="bannerList"></NxSlider>
				
				<view class="goods-list">
					<template v-for="(category,catIndex) in formatData">
						
					<view v-if="category.children.length" :key="catIndex" class="goods-type">
						<view class="hd">
							<text class="cate-title">{{category.name}}</text>
							<image class="cate-img" :src="category.icon"></image>
						</view>
						<view v-for="(good,index) in category.children" :key="index" class="goods-item">
							<image class="thumb" :src="good.img"></image>	
							<view class="context">
								<view class="title-wrap"><text class="title">{{good.name}}</text></view>
								<view class="desc-wrap"><text class="desc">{{good.description}}</text></view>
								<view class="attr">
									<view class="wrap">
										<text class="pre">￥</text>
										<text class="price">{{good.price}}</text>
									</view>
									<view class="state-wrap">
										<text v-if="good.status===2" class="state-text">已售罄</text>
										<button v-if="good.status===1" class="state-btn">选规格</button>
									</view>
									
								</view>
							</view>
						</view>
					</view>
					
					</template>
				</view>
			</scroll-view>
		</view>
        <!-- <image class="logo" src="../../static/logo.png"></image>
		<view>
            <text class="title">{{title}}</text>
        </view> -->
	</view>
</template>

<script>
	import MainHeader from '@/components/MainHeader'
	import NxSlider from '@/components/NxSlider.vue'
	import {categoryList,bannerList,goodsList} from '@/json.js'
	export default{
		components:{
			MainHeader,
			NxSlider
		},
		data() {
			return {
				categoryList: [],
				curCategory: 1,
				
				bannerList: [],
				goodsList:[]
			}
		},
		computed:{
			formatData()
			{
				let data = this.categoryList.map(category=>{
					let newCate = JSON.parse(JSON.stringify(category))
					newCate.children=[]
					this.goodsList.forEach(good=>{
						if(good.category===category.id){
							newCate.children.push(good)
						}
					})
					return newCate;
				})
				return data;
			}
		},
		onLoad() {
			this.categoryList = categoryList
			this.bannerList = bannerList
			this.goodsList = goodsList
			this.format
		},
		methods: {
			
		}
	};
</script>

<style  lang="scss" scoped>
	.app-content{
		position: fixed;
		top:142rpx;
		margin-top: var(--status-bar-height);
		left: 0;
		right: 0;
		bottom:var(--window-bottom)
	}
    .menu-list{
      width: 160rpx;
      top: 0;
      bottom: 0;
      background-color: #f8f8f8;
    }
    .menu-item{
      background-color: #f8f8f8;
      padding-left:20rpx;
      padding-right:20rpx;
      padding-top:32rpx;
      padding-bottom:32rpx;
    }
    .menu-text{
      font-size: 22rpx;
      color: #a5a5a5;
    }
    .menu-active{
      background-color: #fff;
    }
	
	.right{
		flex:1;
		margin-right: 20rpx;
		margin-left: 20rpx;
	}
	.goods-list{
		margin-top:40rpx;
		.hd{
			display: flex;	
			justify-content: flex-start;
			.cate-title{
				font-size: 24rpx;
				margin-right: 10rpx;
			}
			.cate-img{
				width: 24rpx;
				height: 24rpx;
			}
		}
		.goods-item{
			display: flex;
			padding-top: 40rpx;
			padding-bottom: 40rpx;
			overflow: hiden;
		}
		.thumb{
			width: 150rpx;
			height: 150rpx;
			margin-right: 20rpx;
		}
		.context{
			width: 380rpx;
			overflow: hidden;
		}
		.title-wrap{
			overflow: hidden;
			text-overflow:ellipsis;
			white-space: nowrap;
			// height: 30rpx;
			line-height: 30rpx;
			margin-bottom: 10rpx;
		}
		.title{
			font-size: 30rpx;
		}
		.desc-wrap{
			overflow: hidden;
			text-overflow:ellipsis;
			white-space: nowrap;
			line-height: 24rpx;
			line-height: 24rpx;
			margin-bottom:20rpx;
		}
		.desc{
			color: #999999;
			font-size: 24rpx;
		}
		.attr{
			display: flex;
			justify-content: space-between;
			align-items: center;
			
			.pre{
				font-size: 24rpx;
			}
			.price{
				font-size: 34rpx;
			}
			
			.state-text{
				font-size: 24rpx;
				color: #999;
			}
			.state-btn{
				width: 130rpx;
				height: 48rpx;
				background-color: #cba13f;
				line-height: 48rpx;
				color: #fff;
				font-size: 24rpx;
				border-radius: 24rpx;
			}
		}
		
		
		
	}
	
</style>
