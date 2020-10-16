<template>
	<view>
		<!-- 标签页 -->
		
		<view style="margin:5%;">攻略推荐</view>
		
			<view v-for="item in recommends" :key='index'>
					<view v-for="(item,index) in recommends" :key='index' style="width: 95%;background-color: #FFFFFF;margin-left: 2.5%;margin-top: 2%;" @click="particulars(item,index)">
						<view>
							<image style="width: 100%;height: 330rpx;border-radius: 5px;" :src="item.strategy"></image>
						</view>
						<view style="width: 96%;display: flex;justify-content: space-between;line-height: 50rpx;margin-left: 2%;padding-top: 20px;padding-bottom: 20px;">
							<view>{{item.name}}</view>
							<view>{{item.named}}</view>
						</view>
					</view>
			</view>
		
		<!-- 标签页 -->
	</view>
	
</template>

<script>
	import json from '../../testdata/index.json'; //引入js文件
	export default {
		data() {
			return {
				recommends:''
			}
		},
		methods: {
		
			particulars(res,index){
				var data = res.name
				var img = res.strategy
				uni.navigateTo({
					url:'../gorge/gorge?data='+data +'&index='+index+'&img='+img
				})
			}
			
		},
		onLoad() {
			this.recommends = json.recommend
			
		}
	}
</script>

<style>
body{
	background-color: #DCDEE0;
}
</style>
