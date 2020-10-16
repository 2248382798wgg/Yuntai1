<template>
	<view class="content">
		<van-collapse :value="activeNames" @change="onChange" @open="onOpen" @close="onClose">
			<van-collapse-item title="红石峡" name="1">
				<view class="block" v-for="item in items" @click="bonus(item,index)">
					<view class="blockone">
						<view class="left">
							<image :src="item.img"></image>
						</view>
						<view class="right">
							<view>{{item.name}}</view>
							<view>{{item.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
			<van-collapse-item title="茱峰" name="2">
				<view class="block" v-for="itemtwo in itemtwo">
					<view class="blockone">
						<view class="left">
							<image :src="itemtwo.img"></image>
						</view>
						<view class="right">
							<view>{{itemtwo.name}}</view>
							<view>{{itemtwo.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
			<van-collapse-item title="泉瀑峡" name="3">
				<view class="block" v-for="itemthree in itemthree">
					<view class="blockone">
						<view class="left">
							<image :src="itemthree.img"></image>
						</view>
						<view class="right">
							<view>{{itemthree.name}}</view>
							<view>{{itemthree.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
			<van-collapse-item title="潭瀑峡" name="4">
				<view class="block" v-for="itemfour in itemfour">
					<view class="blockone">
						<view class="left">
							<image :src="itemfour.img"></image>
						</view>
						<view class="right">
							<view>{{itemfour.name}}</view>
							<view>{{itemfour.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
			<van-collapse-item title="云溪谷" name="5">
				<view class="block" v-for="itemfive in itemfive">
					<view class="blockone">
						<view class="left">
							<image :src="itemfive.img"></image>
						</view>
						<view class="right">
							<view>{{itemfive.name}}</view>
							<view>{{itemfive.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
			<van-collapse-item title="猕猴谷" name="6">
				<view class="block" v-for="itemsix in itemsix">
					<view class="blockone">
						<view class="left">
							<image :src="itemsix.img"></image>
						</view>
						<view class="right">
							<view>{{itemsix.name}}</view>
							<view>{{itemsix.icon}}</view>
						</view>
					</view>
				</view>
			</van-collapse-item>
		</van-collapse>
	</view>
	
</template>


<script>
	export default {
		data() {
			return {
				activeNames: ["1"],
				items: [{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "红石峡",
						icon: ">"
					},
					{
						img: "../../static/imgfour.png",
						name: "子房湖水上乐园",
						icon: ">"
					},
					{
						img: "../../static/imgeight.png",
						name: "白龙瀑",
						icon: ">"
					},
					{
						img: "../../static/imgfourr.png",
						name: "龟背石",
						icon: ">"
					},
					{
						img: "../../static/imgnight.png",
						name: "黑龙洞",
						icon: ">"
					},
					{
						img: "../../static/imgone.png",
						name: "玉面大佛",
						icon: ">"
					},
					{
						img: "../../static/imgselevent.png",
						name: "一线天",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "同心如意桥",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "黄龙铺",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "钟乳石",
						icon: ">"
					}
				],
				itemtwo: [{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "茱啥峰",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "玄帝宫",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "药王洞",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "凤凰岭",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "重阳阁",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "云台山",
						icon: ">"
					}
				],
				itemthree: [{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "泉瀑峡",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "泉瀑峡主题碑",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "幽谭",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "云台天瀑",
						icon: ">"
					}

				],
				itemfour: [{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "潭瀑峡",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "情人瀑",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "寿仙石",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "金龙我播",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "丫字瀑",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "清漪池",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "水帘洞",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "不老泉",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "洗砚池",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "试剑石",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "水帘瀑",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "坐井观天",
						icon: ">"
					}
				],
				itemfive: [{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "火光海",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "梦幻溪谷",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "海底世界",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "月老怪石",
						icon: ">"
					},

					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "竹林光影",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "云台山母秀",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "双子喊泉",
						icon: ">"
					},
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "石影太极",
						icon: ">"
					}
				],
				itemsix:[
					{
						img: "../../static/692b5e8bf4bd5c29bd1db3b3a262397.png",
						name: "猕猴谷",
						icon: ">"
					}
				]


			}
		},
		onLoad() {

		},
		methods: {
			onChange(event) {
				console.log(event)
				this.activeNames = event.detail
			},
			onOpen(event) {
				// Toast(`展开: ${event.detail}`);
			},
			onClose(event) {
				// Toast(`关闭: ${event.detail}`);
			}
			// bonus(res,id) {
			// 	var img = res.img
			// 	uni.navigateTo({
			// 		url:'../dragon/dragon?img=' + img
			// 	})
			// }
		}
	}
</script>
<style>
	.content {
		background-color: #FFFFFF;
	}

	/deep/.van-collapse-item {
		padding-top: 4%;
		padding-bottom: 4%;
		font-size: 100rpx;
		height: auto;
	}

	.van-cell__title {
		font-size: 25px;
		font-weight: 500;
	}

	.block {
		height: auto;
		padding: 3%;
	}

	.blockone {
		display: flex;
		width: 100%;
		border-bottom: 1rpx solid #E8E8E8;
		padding-bottom: 2.5%;
		margin-bottom: 3.5%;
	}

	.blockone image {
		width: 100rpx;
		height: 60rpx;

	}

	.left {
		width: 15%;
	}

	.right {
		display: flex;
		justify-content: space-between;
		width: 80%;
		margin-left: 2.5%;
		font-size: 30rpx;
		line-height: 33px;
		color: #333333;
	}
</style>
