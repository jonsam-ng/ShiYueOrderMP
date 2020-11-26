<template>
	<view class="content">
		<!-- Category Menu -->
		<category :categoryList="categoryList" :subCategoryList="subCategoryList" @categoryMainClick="categoryMainClick"
		 @categorySubClick="categorySubClick" />
		<!-- Cart -->
		<cart />
	</view>
</template>

<script>
	import category from "../../components/qiyue-category/qiyue-category.vue"
	import cart from "../../components/cart/cart.vue"
	export default {
		data() {
			return {
				categoryList: [],
				subCategoryList: []
			}
		},
		components: {
			category,
			cart
		},
		methods: {
			categoryMainClick(category) {
				this.subCategoryList = category.subCategoryList;
			},
			categorySubClick(category) {
				console.log(category);
			}
		},
		mounted() {
			for (var i = 0; i < 20; i++) {
				var subList = [];
				for (var j = 0; j < 30; j++) {
					subList.push({
						"name": "分类" + i + ":商品" + j,
						"logo": "http://placehold.it/50x50"
					})
				}
				this.categoryList.push({
					"name": "分类" + i,
					"subCategoryList": subList
				})
			}
			this.subCategoryList = this.categoryList[0].subCategoryList;
		}
	}
</script>

<style>

</style>
