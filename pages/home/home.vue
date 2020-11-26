<!-- Home -->
<template>
	<view class="content">
		<!-- Slider -->
		<view class="slider-wrapper">
			<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="3000">
				<swiper-item>
					<view class="swiper-item uni-bg-red">A</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green">B</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-blue">C</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- Banner -->
		<view class="banner-wrapper">
			<view class="banner-inner-wrapper">
				<view class="banner-tip">
					<text class="tip-h1">手机点餐</text>
					<text class="tip-h2">无需排队，快速下单</text>
				</view>
				<view class="banner-img">
					<image src="../../static/image/home/food.png" mode="aspectFill" class="banner-food" />
				</view>
			</view>
		</view>
	</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		components: {

		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		.slider-wrapper {
			width: 100%;
			height: 400rpx;

			.swiper {
				height: 100%;

				.swiper-item {
					width: 100%;
					height: 100%;

					&.uni-bg-red {
						background-color: red;
					}

					&.uni-bg-green {
						background-color: green;
					}

					&.uni-bg-blue {
						background-color: blue;
					}
				}
			}
		}

		.banner-wrapper {
			width: 100%;
			height: 320rpx;
			.banner-inner-wrapper {
				display: flex;
				align-items: center;
				justify-content: center;
				margin: 35rpx 20rpx;
				box-shadow: 0 0 5px 5px rgba($color: #676767, $alpha: .3);
				height: 100%;
				border-radius: 10rpx;

				.banner-tip {
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					height: 100%;
					width: 50%;
					.tip-h1{
						font-size: 60rpx;
						font-weight: bold;
						word-spacing: 1.1rem;
						color: $uni-text-color;
					}
					.tip-h2{
						font-size: 30rpx;
						font-weight: normal;
						word-spacing: normal;
						color: $uni-text-color-second;
					}
				}

				.banner-img {
					height: 100%;
					width: 50%;
					display: flex;
					align-items: center;
					justify-content: center;

					.banner-food {
						width: 200rpx;
						height: 200rpx;
					}
				}
			}

		}
	}
</style>
