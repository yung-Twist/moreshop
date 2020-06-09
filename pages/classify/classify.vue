<template>
	<view class="u-wrap">
		<view class="u-search-box">
			<view class="u-search-inner">
				<u-icon name="search" color="#909399" :size="28"></u-icon>
				<text class="u-search-text">搜索uView</text>
			</view>
		</view>
		<view class="u-menu-wrap">
			<scroll-view scroll-y scroll-with-animation class="u-tab-view menu-scroll-view" :scroll-top="scrollTop">
				<view v-for="(item,index) in tabbar" :key="index" class="u-tab-item" :class="[current==index ? 'u-tab-item-active' : '']"
				 :data-current="index" @tap.stop="swichMenu(index)">
					<text class="u-line-1">{{item.name}}</text>
				</view>
			</scroll-view>
			<block v-for="(item,index) in tabbar" :key="index">
				<scroll-view scroll-y class="right-box" v-if="current==index">
					<view class="page-view">
						<view class="class-item">
							<view class="item-title">
								<text>{{item.name}}</text>
							</view>
							<view class="item-container">
								<view class="thumb-box" v-for="(item1, index1) in item.foods" :key="index1">
									<image class="item-menu-image" :src="item1.icon" mode=""></image>
									<view class="item-menu-name">{{item1.name}}</view>
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabbar: [
					{
						"name": "女装",
						"foods": [{
								"name": "A字裙",
								"key": "A字裙",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/1.jpg",
								"cat": 10
							},
							{
								"name": "T恤",
								"key": "T恤",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/2.jpg",
								"cat": 10
							},
							{
								"name": "半身裙",
								"key": "半身裙",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/3.jpg",
								"cat": 10
							},
							{
								"name": "衬衫",
								"key": "衬衫",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/4.jpg",
								"cat": 10
							},
							{
								"name": "短裙",
								"key": "短裙",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/5.jpg",
								"cat": 10
							},
							{
								"name": "阔腿裤",
								"key": "阔腿裤",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/6.jpg",
								"cat": 10
							},
							{
								"name": "连衣裙",
								"key": "连衣裙",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/7.jpg",
								"cat": 10
							},
							{
								"name": "妈妈装",
								"key": "妈妈装",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/8.jpg",
								"cat": 10
							},
							{
								"name": "牛仔裤",
								"key": "牛仔裤",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/9.jpg",
								"cat": 10
							},
							{
								"name": "情侣装",
								"key": "情侣装",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/10.jpg",
								"cat": 10
							},
							{
								"name": "休闲裤",
								"key": "休闲裤",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/11.jpg",
								"cat": 10
							},
							{
								"name": "雪纺衫",
								"key": "雪纺衫",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/12.jpg",
								"cat": 10
							},
							{
								"name": "防晒衣",
								"key": "防晒衣",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/13.jpg",
								"cat": 10
							},
							{
								"name": "礼服/婚纱",
								"key": "礼服婚纱",
								"icon": "https://cdn.uviewui.com/uview/common/classify/1/14.jpg",
								"cat": 10
							}
						]
					},
					{
						"name": "美食",
						"foods": [{
								"name": "火锅",
								"key": "火锅",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/1.jpg",
								"cat": 6
							},
							{
								"name": "糕点饼干",
								"key": "糕点饼干",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/2.jpg",
								"cat": 6
							},
							{
								"name": "坚果果干",
								"key": "坚果果干",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/3.jpg",
								"cat": 6
							},
							{
								"name": "酒类",
								"key": "酒类",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/4.jpg",
								"cat": 6
							},
							{
								"name": "辣条",
								"key": "辣条",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/5.jpg",
								"cat": 6
							},
							{
								"name": "大礼包",
								"key": "大礼包",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/6.jpg",
								"cat": 6
							},
							{
								"name": "精品茗茶",
								"key": "茶",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/7.jpg",
								"cat": 6
							},
							{
								"name": "休闲食品",
								"key": "休闲食品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/8.jpg",
								"cat": 6
							},
							{
								"name": "糖果巧克力",
								"key": "糖果巧克力",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/9.jpg",
								"cat": 6
							},
							{
								"name": "方便速食",
								"key": "方便速食",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/10.jpg",
								"cat": 6
							},
							{
								"name": "营养代餐",
								"key": "营养代餐",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/11.jpg",
								"cat": 6
							},
							{
								"name": "粮油副食",
								"key": "粮油",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/12.jpg",
								"cat": 6
							},
							{
								"name": "生鲜水果",
								"key": "水果",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/13.jpg",
								"cat": 6
							},
							{
								"name": "饮品",
								"key": "饮品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/2/14.jpg",
								"cat": 6
							}
						]
					},
					{
						"name": "美妆",
						"foods": [{
								"name": "化妆刷",
								"key": "化妆刷",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/1.jpg",
								"cat": 3
							},
							{
								"name": "粉底",
								"key": "粉底",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/2.jpg",
								"cat": 3
							},
							{
								"name": "洗发护发",
								"key": "洗发护发",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/3.jpg",
								"cat": 3
							},
							{
								"name": "美容工具",
								"key": "美容工具",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/4.jpg",
								"cat": 3
							},
							{
								"name": "眼部护理",
								"key": "眼部护理",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/5.jpg",
								"cat": 3
							},
							{
								"name": "眉妆",
								"key": "眉妆",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/6.jpg",
								"cat": 3
							},
							{
								"name": "卸妆品",
								"key": "卸妆品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/7.jpg",
								"cat": 3
							},
							{
								"name": "基础护肤",
								"key": "基础护肤",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/8.jpg",
								"cat": 3
							},
							{
								"name": "眼妆",
								"key": "眼妆",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/9.jpg",
								"cat": 3
							},
							{
								"name": "唇妆",
								"key": "唇妆",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/10.jpg",
								"cat": 3
							},
							{
								"name": "面膜",
								"key": "面膜",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/11.jpg",
								"cat": 3
							},
							{
								"name": "沐浴用品",
								"key": "沐浴用品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/12.jpg",
								"cat": 3
							},
							{
								"name": "护肤套装",
								"key": "护肤套装",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/13.jpg",
								"cat": 3
							},
							{
								"name": "防晒品",
								"key": "防晒品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/14.jpg",
								"cat": 3
							},
							{
								"name": "美甲",
								"key": "美甲",
								"icon": "https://cdn.uviewui.com/uview/common/classify/3/15.jpg",
								"cat": 3
							}

						]
					},
					{
						"name": "居家日用",
						"foods": [{
								"name": "垃圾袋",
								"key": "垃圾袋",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/1.jpg",
								"cat": 4
							},
							{
								"name": "纸巾",
								"key": "纸巾",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/2.jpg",
								"cat": 4
							},
							{
								"name": "驱蚊用品",
								"key": "驱蚊用品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/3.jpg",
								"cat": 4
							},
							{
								"name": "收纳神器",
								"key": "收纳神器",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/4.jpg",
								"cat": 4
							},
							{
								"name": "厨房用品",
								"key": "厨房用品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/5.jpg",
								"cat": 4
							},
							{
								"name": "厨房烹饪",
								"key": "烹饪",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/6.jpg",
								"cat": 4
							},
							{
								"name": "衣物晾晒",
								"key": "衣物晾晒",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/7.jpg",
								"cat": 4
							},
							{
								"name": "衣物护理",
								"key": "衣物护理",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/8.jpg",
								"cat": 4
							},
							{
								"name": "宠物用品",
								"key": "宠物用品",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/9.jpg",
								"cat": 4
							},
							{
								"name": "医药保健",
								"key": "医药",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/10.jpg",
								"cat": 4
							},
							{
								"name": "日用百货",
								"key": "百货",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/11.jpg",
								"cat": 4
							},
							{
								"name": "清洁用品",
								"key": "清洁",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/12.jpg",
								"cat": 4
							},
							{
								"name": "绿植园艺",
								"key": "绿植",
								"icon": "https://cdn.uviewui.com/uview/common/classify/4/13.jpg",
								"cat": 4
							}
						]
					},
			
				],
				scrollTop: 0, //tab标题的滚动条位置
				current: 0, // 预设当前项的值
				menuHeight: 0, // 左边菜单的高度
				menuItemHeight: 0, // 左边菜单item的高度
			}
		},
		computed: {

		},
		methods: {
			getImg() {
				return Math.floor(Math.random() * 35);
			},
			// 点击左边的栏目切换
			async swichMenu(index) {
				if (index == this.current) return;
				this.current = index;
				// 如果为0，意味着尚未初始化
				if (this.menuHeight == 0 || this.menuItemHeight == 0) {
					await this.getElRect('menu-scroll-view', 'menuHeight');
					await this.getElRect('u-tab-item', 'menuItemHeight');
				}
				// 将菜单菜单活动item垂直居中
				this.scrollTop = index * this.menuItemHeight + this.menuItemHeight / 2 - this.menuHeight / 2;
			},
			// 获取一个目标元素的高度
			getElRect(elClass, dataVal) {
				new Promise((resolve, reject) => {
					const query = uni.createSelectorQuery().in(this);
					query.select('.' + elClass).fields({
						size: true
					}, res => {
						// 如果节点尚未生成，res值为null，循环调用执行
						if (!res) {
							setTimeout(() => {
								this.getElRect(elClass);
							}, 10);
							return;
						}
						this[dataVal] = res.height;
					}).exec();
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.u-wrap {
		height: calc(100vh);
		/* #ifdef H5 */
		height: calc(100vh - var(--window-top));
		/* #endif */
		display: flex;
		flex-direction: column;
	}

	.u-search-box {
		padding: 18rpx 30rpx;
	}

	.u-menu-wrap {
		flex: 1;
		display: flex;
		overflow: hidden;
	}

	.u-search-inner {
		background-color: rgb(234, 234, 234);
		border-radius: 100rpx;
		display: flex;
		align-items: center;
		padding: 10rpx 16rpx;
	}

	.u-search-text {
		font-size: 26rpx;
		color: $u-tips-color;
		margin-left: 10rpx;
	}

	.u-tab-view {
		width: 200rpx;
		height: 100%;
	}

	.u-tab-item {
		height: 110rpx;
		background: #f6f6f6;
		box-sizing: border-box;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 26rpx;
		color: #444;
		font-weight: 400;
		line-height: 1;
	}

	.u-tab-item-active {
		position: relative;
		color: #000;
		font-size: 30rpx;
		font-weight: 600;
		background: #fff;
	}

	.u-tab-item-active::before {
		content: "";
		position: absolute;
		border-left: 4px solid $u-type-primary;
		height: 32rpx;
		left: 0;
		top: 39rpx;
	}

	.u-tab-view {
		height: 100%;
	}

	.right-box {
		background-color: rgb(250, 250, 250);
	}

	.page-view {
		padding: 16rpx;
	}

	.class-item {
		margin-bottom: 30rpx;
		background-color: #fff;
		padding: 16rpx;
		border-radius: 8rpx;
	}

	.item-title {
		font-size: 26rpx;
		color: $u-main-color;
		font-weight: bold;
	}

	.item-menu-name {
		font-weight: normal;
		font-size: 24rpx;
		color: $u-main-color;
	}

	.item-container {
		display: flex;
		flex-wrap: wrap;
	}

	.thumb-box {
		width: 33.333333%;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		margin-top: 20rpx;
	}

	.item-menu-image {
		width: 120rpx;
		height: 120rpx;
	}
</style>
