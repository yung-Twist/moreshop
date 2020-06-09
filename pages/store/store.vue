<template>
	<view>
		<text>门店</text>
		<view class="coupon"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				storedata:[
					{
						storeName:'花果山',
						storeGoods:[
							{
								name:'ss'
							}
						]
					}
				]
			};
		}
	}
</script>

<style lang="scss">
.coupon{
  width: 300px;
  height: 100px;
  position: relative;
  background: radial-gradient(circle at right bottom, transparent 10px, #ffffff 0) top right /50% 51px no-repeat,
    radial-gradient(circle at left bottom, transparent 10px, #ffffff 0) top left / 50% 51px no-repeat,
    radial-gradient(circle at right top, transparent 10px, #ffffff 0) bottom right / 50% 51px no-repeat,
    radial-gradient(circle at left top, transparent 10px, #ffffff 0) bottom left / 50% 51px no-repeat;
  filter: drop-shadow(2px 2px 2px rgba(0,0,0,.2));
}
</style>
