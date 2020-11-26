<template>
	<view class="content">
		<!-- Avatar -->
		<view class="avatar-wrapper">
			<view class="avatar-user-info">
				<!--  put user avatar here -->
				<text>jonsam ng</text>
			</view>
			<view class="avatar-user-data">
				<view class="user-data" v-for="(data, index) in userData" key={data.key}>
					<text class="user-data-text">{{data.text}}</text>
					<text class="user-data-value">{{data.value}}</text>
				</view>
			</view>
		</view>
		<!-- Cells -->
		<view class="cells-wrapper">
			<adCell text="会员等级" icon="../../static/image/me/diamond.png" :showBottomLine="true" />
			<adCell text="会员码" icon="../../static/image/me/vip.png" :showBottomLine="true" />
			<adCell text="积分商城" icon="../../static/image/me/store.png" :showBottomLine="true" />
			<adCell text="我的订单" icon="../../static/image/me/order.png" :showBottomLine="true" />
			<adCell text="收货地址" icon="../../static/image/me/address.png" :showBottomLine="true" />
			<adCell text="兑换码" icon="../../static/image/me/gift.png" :showBottomLine="true" />
			<adCell text="平台须知" icon="../../static/image/me/note.png" :showBottomLine="true" />
			<adCell text="版本号" :showArrow="false" icon="../../static/image/me/info.png" :showBottomLine="true" detail=" 食悦 1.0.0" />
		</view>
	</view>
</template>

<script>
	import adCell from "../../components/andy-adcell/andy-adcell.vue"
	export default {
		data() {
			return {
				userData: [{
						key: "score",
						text: "积分",
						value: 0
					},
					{
						key: "money",
						text: "储值金",
						value: 0
					},
					{
						key: "coupon",
						text: "优惠券",
						value: 0
					}
				]
			}
		},
		components: {
			adCell
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.avatar-wrapper {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
		width: 100%;
		padding: 10rpx 0;

		.avatar-user-info {}

		.avatar-user-data {
			width: 100%;
			display: flex;
			justify-content: space-between;
			align-items: center;

			.user-data {
				flex: 1;
				height: 100rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				flex-direction: column;
				border-right: 1px solid #ccc;

				&:last-of-type {
					border-right: none;
				}

				.user-data-text {
					font-size: 32rpx;
					color: $uni-text-color-second;
					font-weight: 400;
				}
				.user-data-value {
					font-size: 52rpx;
					color: $uni-color-primary;
					font-weight:800;
				}
			}
		}
	}
</style>
