<template>
	<uni-swipe-action>
		<uni-swipe-action-item :options="swipeOptions" @click="swipeClick" @change="swipeChange">
			<view class="adBaseView" hover-class="baseViewHover" :style="{backgroundColor:backgroundColor}" @click="onClick">
				<view class="adRowView">
					<image class="icon" :src="icon" :style="{marginRight: iconRight + 'upx'}" mode="aspectFit" v-if="icon != ''"></image>
					<view class="headView" v-if="text != ''">
						<view class="textView" :style="{color:textColor}">{{text}}</view>
						<view class="mustView" v-if="mustInput === true || mustInput === 'true'">*</view>
					</view>
					<view class="detailView1" :style="{color:detailColor}" v-if="detail != ''">{{detail}}</view>
					<slot></slot>
					<view class="iconfont arrowView" v-if="showArrow === true || showArrow === 'true'"></view>
				</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note != null && note != ''">{{note}}</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note1 != null && note1 != ''">{{note1}}</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note2 != null && note2 != ''">{{note2}}</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note3 != null && note3 != ''">{{note3}}</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note4 != null && note4 != ''">{{note4}}</view>
				<view class="detailView2" :style="{color:noteColor}" v-if="note5 != null && note5 != ''">{{note5}}</view>
				<view class="bottomLine" v-if="showBottomLine === true || showBottomLine === 'true'"></view>
			</view>
		</uni-swipe-action-item>
	</uni-swipe-action>
</template>

<script>
	import uniSwipeAction from '../swipe-action/uni-swipe-action/uni-swipe-action.vue';
	import uniSwipeActionItem from '../swipe-action/uni-swipe-action-item/uni-swipe-action-item.vue';

	export default {
		name: 'adCell',
		components: {
			uniSwipeAction,
			uniSwipeActionItem
		},
		props: {
			// 左侧图标
			icon: {
				type: String,
				default: ""
			},
			// 图片右侧于文字的间距
			iconRight: {
				type: String,
				default: "10"
			},
			// 主文本
			text: String,
			// 主文本颜色
			textColor: {
				type: String,
				default: "#5E5E5E"
			},
			// 是否必填
			mustInput: {
				type: [Boolean, String],
				default: false
			},
			// 副文本
			detail: String,
			// 副文本颜色
			detailColor: {
				type: String,
				default: "#B3B3B3"
			},
			// 子文本1
			note: String,
			// 子文本2
			note1: String,
			// 子文本3
			note2: String,
			// 子文本4
			note3: String,
			// 子文本5
			note4: String,
			// 子文本6
			note5: String,
			// 子文本颜色
			noteColor: {
				type: String,
				default: "#B3B3B3"
			},
			// 是否显示右侧箭头图标
			showArrow: { //是否显示箭头
				type: [Boolean, String],
				default: true
			},
			// cell背景色
			backgroundColor: {
				type: String,
				default: "#FFFFFF"
			},
			// 是否显示底部分割线，默认true
			showBottomLine: {
				type: [Boolean, String],
				default: true
			},
			// 左滑选项
			swipeOptions: {
				type: Array,
				default () {
					return [];
				}
			},
		},
		data() {
			return {

			}
		},
		methods: {
			// 点击Cell
			onClick() {
				this.$emit('click')
			},
			// 点击左滑出来的按钮
			swipeClick(e) {
				this.$emit('swipeClick', e)
			},
			// 左滑开启状态
			swipeChange(open) {
				this.$emit('swipeChange', open)
			},
		}
	}
</script>

<style>
	@font-face {
		font-family: 'iconfont';
		src: url('iconfont.ttf') format('truetype');
	}

	.iconfont {
		font-family: "iconfont";
		font-size: 15px;
		color: #BBBBBB;
		font-weight: bold;
		font-style: normal;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}

	.arrowView:before {
		content: "\e64a";
	}

	.adBaseView {
		width: 100%;
		background-color: #FFFFFF;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding-top: 30upx;
	}

	.baseViewHover {
		background-color: #F3F3F3;
	}

	.adRowView {
		width: calc(100% - 48upx);
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.headView {
		flex: 1;
		text-align: left;
		margin-left: 30upx;
		font-size: 28upx;
		/*超出一行点点点*/
		overflow: hidden;
		/*超出的部分隐藏起来。*/
		white-space: nowrap;
		/*不显示的地方用省略号...代替*/
		text-overflow: ellipsis;
		/* 支持 IE */

		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.textView {
		text-align: left;
		margin-left: 30upx;
		font-size: 28upx;
		/*超出一行点点点*/
		overflow: hidden;
		/*超出的部分隐藏起来。*/
		white-space: nowrap;
		/*不显示的地方用省略号...代替*/
		text-overflow: ellipsis;
		/* 支持 IE */
	}

	.mustView {
		color: red;
		font-size: 32upx;
		margin-left: 10upx;
	}

	.detailView1 {
		flex: 1;
		text-align: right;
		font-size: 28upx;
		overflow: hidden;
		/*超出的部分隐藏起来。*/
		white-space: nowrap;
		/*不显示的地方用省略号...代替*/
		text-overflow: ellipsis;
		/* 支持 IE */
	}

	.detailView2 {
		width: calc(100% - 48upx);
		text-align: left;
		font-size: 28upx;
		word-wrap: break-word;
		word-break: normal;
		margin-top: 12upx;
	}

	.bottomLine {
		width: 95%;
		height: 1upx;
		background-color: #DDDDDD;
		margin-top: 30upx;
	}

	.icon {
		width: 38upx;
		height: 38upx;
		margin-right: 10upx;
	}
</style>
