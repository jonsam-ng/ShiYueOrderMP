<template>
	<view class="cart-content">
		<view class="cart-inner-wrapper">
			<view class="cart-list-toggle">
				<view class="cart-list-toggle-inner">
					<uni-badge text="2" type="error" class="cart-badge" />
				</view>
			</view>
			<view class="cart-price">
				<text>￥{{price}}</text>
			</view>
			<view class="cart-order">
				<text>去结算</text>
			</view>
		</view>
	</view>
</template>

<script>
	import uniBadge from "../uni-badge/uni-badge.vue"
	export default {
		data() {
			return {
				price: 0,
			};
		},
		components: {
			uniBadge
		}
	}
</script>

<style lang="scss">
	.cart-content {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		background-color: #e8e7f4;
		height: 100rpx;
		border-top-right-radius: 40rpx;
		border-top-left-radius: 40rpx;

		.cart-inner-wrapper {
			height: 100%;
			width: 100%;
			display: flex;
			align-items: center;
			justify-content: center;
			position: relative;

			.cart-list-toggle {
				position: absolute!important;
				width: 120rpx;
				height: 120rpx;
				border-radius: 50% 50%;
				background-color: #FFFFFF;
				position: relative;
				left: 50rpx;
				bottom: 35rpx;
				display: flex;
				justify-content: center;
				align-items: center;
				box-sizing: border-box;
				margin: none;
				border: none;
				outline: none;

				.cart-list-toggle-inner {
					background-image: url(../../static/image/menu/cart.png);
					background-position: center center;
					background-size: contain;
					background-repeat: no-repeat;
					height: 50%;
					width: 50%;
				}

				.cart-badge {
					position: absolute;
					top: 0px;
					right: 0rpx;

				}

			}

			.cart-price {
				width: 70%;
				height: 100%;
				text-align: center;
				display: flex;
				align-items: center;
				justify-content: flex-start;
				color: $uni-text-color;
				padding-left: 80rpx;

			}

			.cart-order {
				width: 30%;
				height: 100%;
				text-align: center;
				display: flex;
				align-items: center;
				justify-content: center;
				background-color: $uni-color-primary;
				color: #FFFFFF;
				border-top-right-radius: 40rpx;
			}
		}
	}
</style>
