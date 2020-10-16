<template>
	<view>
		<view style="font-size: 40rpx;margin: 3%;">{{title}}</view>
		<view style="margin: 2%;font-size: 20px;font-weight: 700;">{{msg.titone}}</view>
		<view style="padding: 3%;line-height: 28px;">{{msg.onemsg}}</view>
		<view style="margin: 2%;font-size: 20px;font-weight: 700;">{{msg.tittwo}}</view>
		<view style="padding: 3%;">
			<image style="width: 100%;height: 200px;" :src="img"></image>
		</view>
		
	</view>
</template>

<script>
	import json from '../../testdata/index.json'; //引入js文件
	export default {
		data() {
			return {
				title:'',
				img:'',
				msg:''
			}
		},
		methods: {
			
		},
		onLoad(res) {
			console.log(json.gorgeone)
			this.title = res.data
			this.img = res.img
			if(res.index == 0){
				this.msg = json.gorgeone
			}
			if(res.index == 1){
				this.msg = json.gorgetwo
			}
			if(res.index == 2){
				console.log('王格格')
			}
		}
	}
</script>

<style>

</style>
