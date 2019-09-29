<template>
	<view :class="['iconfont',icon]"></view>
</template>

<script lang="ts">
	export default {
	  props:{
		  icon:{
			  type:String,
			  required: true
		  }
	  }
	}
</script>

<style>
</style>
