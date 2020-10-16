<template>
	<view>
		<!-- 标签页 -->
		<van-tabs swipeable :active="active" @change="onChange">
			<view v-for="titled in titled" :key='index'>
				<van-tab :title="titled.name">
					<view v-for="(item,index) in doored" :key='index' style="width: 95%;background-color: #FFFFFF;margin-left: 2.5%;margin-top: 2%;" @click="particulars(item)">
						<view>
							<image style="width: 100%;height: 330rpx;border-radius: 5px;" :src="item.img"></image>
						</view>
						<view style="width: 96%;display: flex;justify-content: space-between;line-height: 50rpx;margin-left: 2%;padding-top: 20px;padding-bottom: 20px;">
							<view>{{item.name}}</view>
							<view>{{item.price}}</view>
						</view>
					</view>
				</van-tab>
			</view>
		</van-tabs>
		<!-- 标签页 -->
	</view>
</template>

<script>
	import json from '../../testdata/index.json'; //引入js文件
	export default {
		data() {
			return {
				active: 0,
				titled: '',
				doored: '',
			}
		},
		methods: {
			onChange(event) {
				// console.log(event.target.index)
				var id = event.target.index;
				if(id == '0'){
					this.doored = json.door
				}
				if(id=='1'){
					this.doored = json.door1
				}
			},
			
			particulars(id) {
				var id = {
					id :id.id,
					img :id.img,
					name :id.name,
					parice:id.price
				}
				uni.navigateTo({
					url: '../particulars/particulars?data=' + encodeURIComponent(JSON.stringify(id))
				})
				
			}
			
		},
		onLoad() {
			this.titled = json.titles
			this.doored = json.door
		}
	}
</script>

<style>
body{
	background-color: #DCDEE0;
}
</style>
