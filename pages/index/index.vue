<template>
	<view style="width: 100%;height: 100%;padding:10px;">
		<button @click="btnGoZhihu" type="primary">模仿知乎</button>
		<button @click="btnGoTantan" type="primary" style="margin-top: 10px;">模仿探探</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			btnGoZhihu(){
				uni.navigateTo({
					url:"../demozhihu/demozhihu"
				})
			},
			btnGoTantan(){
				uni.navigateTo({
					url:"../demotantan/demotantan"
				})
			}
		}
	}
</script>

<style>
	page{
		width: 100%;
		height: 100%;
		overflow: hidden;
	}
	
	view{
		box-sizing: border-box;
	}
	
</style>
