<template>
	<view>
		<!-- 头部 -->
		<!-- <view style="background-color: #00BF45;width: 100%;height: 70px;">
			<view style="text-align: center;padding-top: 6%;font-size: 18px;color: #FFFFFF;">云台山景区</view>
		</view> -->
		<!-- 头部 -->

		<!-- 轮播 -->
		<view>
			<swiper style="width: 100%;height: 250px;" indicator-dots="true" circular="true" autoplay="true">
				<swiper-item v-for="images in images" :key="index">
					<image style="width: 100%;height: 250px;" :src="images.img"></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- 轮播 -->


		<!-- 介绍 -->
		<view>
			<view class="pure_top"></view>

			<view style="display: flex;width: 100%;">
				<view v-for="(shops,index) in shops" :key='index' style="width: 25%;text-align: center;" @click="guide(index)">
					<image style="width: 50%;height: 50px;" :src="shops.shopping"></image>
					<view style="font-size: 15px;">{{shops.name}}</view>
				</view>
			</view>



			<view style="display: flex;width: 100%;margin-top: 3%;">
				<view v-for="sceniced in sceniced" :key='index' style="width: 25%;text-align: center;">
					<image style="width: 50%;height: 50px;" :src="sceniced.picture"></image>
					<view style="font-size: 15px;">{{sceniced.name}}</view>
				</view>
			</view>
		</view>

		<view style="background-color: #F6F8FA;width: 100%;height: 500px;margin-top: 3%;">
			<view style="padding-top: 3%;">
				<view style="background-color: #FFFFFF;width: 100%;height: 50px;">
					<view style="padding: 3%;margin-left: 3%;font-weight: 800;">热门景点</view>

					<!-- 热门景点 -->
					<view style="display: flex;width: 100%;margin-left: 3%;padding-top: 5%;">
						<view v-for="hots in hots" :key='index' style="width: 50%;">
							<view style="font-size: 18px;font-weight: 800;">{{hots.name}}</view>
							<image style="width: 87%;height: 118px;border-radius: 8px;margin-top: 3%;" :src="hots.img"></image>
						</view>
					</view>



					<view style="display: flex;width: 100%;margin-left: 3%;padding-top: 5%;">
						<view v-for="hoteds in hoteds" :key='index' style="width: 50%;">
							<view style="font-size: 18px;font-weight: 800;">{{hoteds.name}}</view>
							<image style="width: 87%;height: 118px;border-radius: 8px;margin-top: 3%;" :src="hoteds.img"></image>
						</view>
					</view>
					<!-- 热门景点 -->
				</view>
			</view>
		</view>
		<!-- 介绍 -->
	</view>
</template>

<script>
	import json from '../../testdata/index.json'; //引入js文件
	export default {
		data() {
			return {
				images: '',
				shops: '',
				sceniced: '',
				hots: '',
				hoteds: ''
			}
		},
		created() {

		},
		onLoad() {
			console.log(json)
			this.images = json.image
			this.shops = json.shop
			this.sceniced = json.scenic
			this.hots = json.hot
			this.hoteds = json.hoted



		},
		methods: {
			guide(e) {
				if(e == 0) {
					
				}
				if(e == 1) {
					
					uni.navigateTo({
						url:'../ticket/ticket'
					})
				}
				if(e == 2) {
					
				}
				if(e == 3) {
					uni.navigateTo({
						url:'../guide/guide'
					})
				}
			}
		}
	}
</script>

<style>
	/* 介绍 */
	.pure_top {
		width: 100%;
		height: 43px;
		position: relative;
		z-index: 999;
		margin-top: -4%;
		overflow: hidden;

	}

	.pure_top::after {
		content: '';
		width: 140%;
		height: 100px;
		position: absolute;
		left: -20%;
		top: 0;
		z-index: -1;
		border-radius: 50% 50% 0 0;
		background: #FFFFFF;
	}

	/* 介绍 */
</style>
