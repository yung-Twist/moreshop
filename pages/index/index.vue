<template>
	<view class="home">
		 <!-- 轮播图 -->
		 <view class="wrap">
			<u-swiper :list="swiperList" name="pic"></u-swiper>
		</view>
		<!-- 商品列表 -->
		<view class="goodsCategoryWrap">
			<view class="goodsCategoryItem" v-for="(item, index) in goodsCagetoryList" :key="index">
				<CagetoryTitle :title="item.categoryName"/>
				<view class="goodsItemWrap">
					<GoodsItemHome :name="item2.name" :pic="item2.pic" :price="item2.price" :originPrice="item2.originPrice" v-for="(item2, index2) in item.goodsList" :key="index2"/>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import GoodsItemHome from '@/myComponents/GoodsItemHome'
	import CagetoryTitle from '@/myComponents/CagetoryTitle'
	export default {
		data() {
			return {
				swiperList:[
					{
						pic:require("@/static/images/swiper/1.png")
					},
					{
						pic:require("@/static/images/swiper/2.png")
					},
					{
						pic:require("@/static/images/swiper/3.png")
					}
				],
				goodsCagetoryList:[
					{
						categoryName:'分类一',
						goodsList:[
							{
								pic:require("@/static/images/swiper/1.png"),
								price:15.4,
								originPrice:34.5,
								name:'富贵花任务'
							},
							{
								pic:require("@/static/images/swiper/2.png"),
								price:15.4,
								originPrice:34.5,
								name:'京挑客'
							},
						]
					},
					{
						categoryName:'分类二',
						goodsList:[
							{
								pic:require("@/static/images/swiper/3.png"),
								price:15.4,
								originPrice:34.5,
								name:'优先贴'
							},
							{
								pic:require("@/static/images/swiper/4.png"),
								price:15.4,
								originPrice:34.5,
								name:'新沂市'
							},
						]
					}
				]
			}
		},
		components:{
			GoodsItemHome,
			CagetoryTitle
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
.home{
	.goodsCategoryWrap{
		.goodsCategoryItem{
			.goodsItemWrap{
				width: 100%;
				display: flex;
				flex-direction: row;
				flex-wrap: wrap;
			}
		}
	}
}
</style>
