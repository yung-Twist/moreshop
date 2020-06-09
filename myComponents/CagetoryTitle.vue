<template>
	<view class="CagetoryTitle">
		<view class="titleName">{{title}}</view>
		<view class="moreGoods">查看更多</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props:{
			title:String
		}
	}
</script>

<style lang="scss">
.CagetoryTitle{
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	padding: 10upx;
	.titleName{
		padding-left: 1em;
		border-left: 2px solid #f40;
		color: #000000;
		font-size: 32upx;
	}
	.moreGoods{
		color: #999999;
		font-size: 32upx;
	}
}
</style>
