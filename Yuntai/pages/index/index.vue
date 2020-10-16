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



		<!-- 天气 -->
		<!-- <view class="weather yesterday">
			<view>
				<view class='date'>今天</view>
				<view class='location'>{{basic.location}}/{{basic.parent_city}}</view>
				<view class='tmp'>{{today.tmp_min}}℃~{{today.tmp_max}}℃</view>
				<view class='cond_txt'>{{today.cond_txt_d}}</view>
			</view>
			<view>
				<view class='weather_icon'>
					<image :src='todyIcon'></image>
				</view>
				<view class='lastUpdateDate'>最后更新：{{update}}</view>
			</view>
		</view>
		<view class="weather today">
			<view>
				<text>明天</text>
				<view class='location'>{{basic.location}}/{{basic.parent_city}}</view>
				<view class='tmp'>{{tomorrow.tmp_min}}℃~{{tomorrow.tmp_max}}℃</view>
				<view class='cond_txt'>{{tomorrow.cond_txt_d}}</view>
			</view>
			<view>
				<view class='weather_icon'>
					<image :src='tomorrowIcon'></image>
				</view>
				<view class='lastUpdateDate'>最后更新：{{update}}</view>
			</view>
		</view>
		<view class="weather tomorrow">
			<view>
				<text>后天</text>
				<view class='location'>{{basic.location}}/{{basic.parent_city}}</view>
				<view class='tmp'>{{afterTomor.tmp_min}}℃~{{afterTomor.tmp_max}}℃</view>
				<view class='cond_txt'>{{afterTomor.cond_txt_d}}</view>
			</view>
			<view>
				<view class='weather_icon'>
					<image :src='afterTomorIcon'></image>
				</view>
				<view class='lastUpdateDate'>最后更新：{{update}}</view>
			</view>
		</view> -->
		<!-- 天气 -->

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
				<view v-for="(sceniced,index) in sceniced" :key='index' style="width: 25%;text-align: center;" @click="user(index)">
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
				hoteds: '',
				// update:'',
				// basic:'',
				// today: '',
				// tomorrow: '',
				// afterTomor: '',
				// todyIcon: '../../static/0.1.jpg',
				// tomorrowIcon: '../../static/0.1.jpg',
				// afterTomorIcon: '../../static/0.1.jpg',
				// longitude:'',
				// latitude:'',
				// wggg:'121'
			}
		},
		onShow(){
			
		},
		created() {
			
		},
		onLoad() {
			this.images = json.image
			this.shops = json.shop
			this.sceniced = json.scenic
			this.hots = json.hot
			this.hoteds = json.hoted
			// this.wgg()
		},
		methods: {
			
			// wgg: async function(){
			// 	uni.getLocation({
			// 		type: 'wgs84',
			// 		success:function(res) {
			// 			var latitude = res.latitude
			// 										var longitude = res.longitude
			// 										var _this = this;
			// 										var key = '30ffef50e6de42f5aaec1b19a742ab8b'; //你自己的key
			// 			var url = 'https://free-api.heweather.com/s6/weather?key=' + key + '&location=' + longitude + ',' + latitude;
			// 			      uni.request({
			// 			        url: url,
			// 			        method: "GET"
			// 			    })
			// 				.then(data => {//data为一个数组，数组第一项为错误信息，第二项为返回数据
			// 				        var [error, res]  = data;
			// 				        console.log(res.data);
			// 						console.log(this.wggg)
			// 				    })
			// 		}
			// 	}) 
				
			
			    
			
			// },
			guide(e) {
				if (e == 0) {
					uni.navigateTo({
						url: '../referral/referral'
					})
				}
				if (e == 1) {

					uni.navigateTo({
						url: '../ticket/ticket'
					})
				}
				if (e == 2) {
					uni.navigateTo({
						url:'../travel/travel'
					})
				}
				if (e == 3) {
					uni.navigateTo({
						url: '../guide/guide'
					})
				}
			},
			user(e) {

				if (e == 0) {
					uni.navigateTo({
						url: '../spot/spot'
					})
				}
				if (e == 1) {
					uni.navigateTo({
						url:'../suggest/suggest'
					})
				}
				if (e == 2) {
					uni.navigateTo({
						url:'../park/park'
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
	.weather {
		height: 110px;
		width: 100%;
		margin-bottom: 10px;
		border-radius: 5px;
		color: #FFF;
		padding: 5PX 15px;
		display: flex;
		font-size: 14px;
		box-sizing: border-box;
	}

	.weather>view {
		flex: 1;
	}

	.weather>view>view {
		margin: 5px 0;
	}

	.yesterday {
		background-color: #30BCAF;
	}

	.today {
		background-color: #78A4be;
	}

	.tomorrow {
		background-color: #FCB654;
	}

	.location,
	.cond_txt {
		font-size: 14px;
	}

	.date,
	.tmp {
		font-weight: bold;
	}

	.weather_icon {
		text-align: center;
		height: 65px;
	}

	.weather_icon image {
		width: 75px;
		height: 100%;
	}

	.lastUpdateDate {
		font-size: 10px;
		text-align: center;
	}
</style>
