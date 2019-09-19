<template>
	<view class="main-header">
		<view class="left">
			<view class="hd">广州番禺万达广场店 ></view>
			<view class="bd">距离您5.1km</view>
		</view>
		<view class="right">
			<switch class="switch" @change="switch2Change" color="#cca33a" />
		</view>
		
	</view>
</template>
	
<script>
	export default {
		data(){
			return {
				
			}
		},
		methods:{
			switch2Change(e){
				
			}
		}
	}
</script>

<style lang="scss" scoped>
	.main-header{
		padding: 5px 5px;
		overflow: hidden;
		.left{
			float: left;	
			text-align:left;
			.hd{
				font-size:18px;
				font-weight: 400;
			}
			.bd{
				font-size: 12px;
				color: #999999;
			}
		}
		.right{
			float:right
		}
		.switch{
			
		}
	}
	
</style>
