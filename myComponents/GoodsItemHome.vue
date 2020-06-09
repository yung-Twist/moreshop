<template>
	<view class="goods-item-home">
		<image :src="pic" mode="" class="goods-item-image"></image>
		<text class="goods-name text-cut">{{name}}</text>
		<view class="goods-price">
			<text class="price">￥{{price}}</text>
			<text class="origin-price">￥{{originPrice}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			name:String,
			pic:String,
			price:Number | String,
			originPrice:Number | String
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.goods-item-home{
	width: 50vw;
	display: flex;
	flex-direction: column;
	.goods-item-image{
		width: 46vw;
		height: 46vw;
	}
	.goods-name{
		font-size: 32upx;
		color: #000;
		font-weight: bold;
		padding-left:1em;
	}
	.goods-price{
		display: flex;
		flex-direction: row;
		align-items: center;
		margin-top: 10upx;
		padding-left:1em;
		.price{
			color: $price;
			font-size: 32upx;
			margin-right: 1em;
		}
		.origin-price{
			@include originPrice();
			font-size: 24upx;
		}
	}
	
}
</style>
