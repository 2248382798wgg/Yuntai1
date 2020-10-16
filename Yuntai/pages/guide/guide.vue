<template>
	<view>
		<!-- 手绘地图、缩放图片开始 -->
		<view v-show="num == 0" style="width: 100%;height: 311px;">
			<view class="page-section">
				<movable-area scale-area style="width: 100%;height: 311px;">
					<movable-view style="width: 100%;height: 311px;" direction="all" @change="onChange" @scale="onScale" scale
					 scale-min="0.5" :scale-value="scale">
						<image src="../../static/@3GBYF8X1414$4B8H4@YA91.png" mode="widthFix"></image>
					</movable-view>
				</movable-area>
			</view>
		</view>
		<!-- 手绘地图结束 -->
		<!-- 实时地图、腾讯地图开始 -->
		<view v-show="num == 1">
			<map style="width: 100%; height:311px;" scale='12' latitude='35.441722' longitude='113.372275'></map>
		</view>
		<!-- 实时地图结束 -->
		<view class="map_tap">
			<view @click="num = 0" :class="{'active':num==0}">
				<view>
					<image src="../../static/ditu.png"></image>
				</view>
				手绘地图
			</view>
			<view @click="getLocation" :class="{'active':num==1}">
				<view>
					<image src="../../static/ditu1.png"></image>
				</view>
				实时地图
			</view>
		</view>
		<view class="integral_product">
			<view class="influence_imaged">
				<view class="banner">
					<view class="chance">
						<view class="one" v-for="(item,index) in guides" :key='index' @click="getMoney(index)">
							<view v-bind:class="{colorChange:index==dynamic}">
								{{item.name}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view style="display: flex;margin-bottom: 4%;">
			<view style="width: 23%;margin: 7%;margin-top: 13%;">
				<view v-for="(item,index) in test" :key='index'>{{item.length}}</view>景点
			</view>
			<view class="influence_imageds">
				<view class="banners">
					<view class="chances">
						<view class="ones" v-for="(item,index) in test" :key='index'>
							<view>
								<view>
									<image style="width: 93%;height:200rpx;border-radius: 8px;" :src="item.img"></image>
								</view>
								{{item.name}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
	
	<!-- <image src="../../static/timg%20(8).jpg"></image> -->
</template>

<script>
	export default {
		data() {
			return {
				num: 0,
				x: 0,
				y: 0,
				scale: 1,
				dynamic: 0,
				length: '',
				test: [{
						img: '../../static/timg%20(5).jpg',
						name: '红石峡'
					},
					{
						img: '../../static/timg%20(3).jpg',
						name: '子房湖水上乐园'
					},
					{
						img: '../../static/timg%20(6).jpg',
						name: '白龙瀑'
					},
					{
						img: '../../static/timg%20(7).jpg',
						name: '龟背石'
					},
					{
						img: '../../static/timg%20(8).jpg',
						name: '黑龙洞'
					},
				],
				guides: [{
						name: '全部'
					},
					{
						name: '茱萸峰'
					},
					{
						name: '泉瀑峡'
					},
					{
						name: '潭暴峡'
					},
					{
						name: '云溪谷'
					},
					{
						name: '猕猴谷'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
					{
						name: '红石峡'
					},
				]
			}
		},
		methods: {
			getMoney(index) {
				//点击添加字体颜色，其他的删除class名称
				this.dynamic = index;

				if (index == '0') {
					var test = [{
							img: '../../static/timg%20(5).jpg',
							name: '红石峡'
						},
						{
							img: '../../static/timg%20(3).jpg',
							name: '子房湖水上乐园'
						},
						{
							img: '../../static/timg%20(6).jpg',
							name: '白龙瀑'
						},
						{
							img: '../../static/timg%20(8).jpg',
							name: '龟背石'
						},
						{
							img: '../../static/timg%20(7).jpg',
							name: '黑龙洞'
						},
					]
					this.test = test;
					this.length = test.length
				}
				if (index == '1') {
					var test = [{
							img: '../../static/ditu1.png',
							name: '2'
						},
						{
							img: '../../static/ditu1.png',
							name: '2'
						},
						{
							img: '../../static/ditu1.png',
							name: '2'
						},
						{
							img: '../../static/ditu1.png',
							name: '2'
						},
						{
							img: '../../static/ditu1.png',
							name: '2'
						},
					]
					this.test = test;
					this.length = test.length
				}
			},
			onChange(e) {},
			onScale(e) {},
			getLocation() {
				this.num = 1;
				uni.getLocation({
					type: 'wgs84',
					success: function(res) {
						console.log('当前位置：' + res.longitude + ',' + res.latitude)
						uni.openLocation({ //​使用微信内置地图查看位置。
							latitude: 35.441722, //要去的纬度-地址
							longitude: 113.372275, //要去的经度-地址
							name: "云台山风景区(请使用高德地图APP体验完整功能)"
						})
					}
				})
			}

		}
	}
</script>

<style>
	.map_tap {
		width: 100%;
		justify-content: flex-end;
		display: flex;
		margin-top: 5%;
	}

	.map_tap view {
		width: 17%;
		text-align: center;
	}

	.map_tap image {
		width: 61rpx;
		height: 59rpx;
		margin-left: 136%;
	}

	.active {
		background-color: #C0C0C0;
		color: #FFFFFF;
		height: 58px;
		
	}

	movable-view {
		width: 100%;
		height: 311rpx;
	}

	movable-area {
		height: 100%;
		width: 30%;
		/* position:fixed; */
		overflow: hidden;
	}

	movable-view image {
		width: 100%;
	}

	.banner {
		width: 100%;
		overflow-x: scroll;
		/*添加横向滚动条*/
		white-space: nowrap;
		/*不换行*/
		width: 100%;
		justify-content: center;
		padding: 2%;
	}

	.one {
		/* width: 40%; */
		display: inline-block;
		text-align: center;
		width: 15%;
		text-align: center;
		margin-top: 3%;

	}

	.colorChange {
		border-radius: 15px 15px;
		background-color: #999999;
		color: #FFFFFF;
	}

	/* .one img {
		width: 50%;
	} */

	.integral_product {
		display: flex;
		width: 100%;
		justify-content: center;
		margin-top: 5%;
	}

	.influence_imaged {
		background-color: #FFFFFF;
		width: 95%;
		height:82px;
		border-radius: 5px;
	}

	.chance {
		margin-top: 5%;
	}

	.influence_imageds {
		width: 77%;
	}

	.banners {
		width: 100%;
		overflow-x: scroll;
		/*添加横向滚动条*/
		white-space: nowrap;
		/*不换行*/
		width: 100%;
		justify-content: center;
		padding: 2%;
	}

	.ones {
		/* width: 40%; */
		display: inline-block;
		text-align: center;
		width: 43%;
		text-align: center;


	}

	.ones image {
		width: 80%;
	}

	.chances {
		margin-top: 2%;
	}
</style>
