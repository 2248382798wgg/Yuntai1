<template>
	<view>
		<view style="font-size: 40rpx;margin: 3%;">{{title}}</view>
		<view style="margin: 2%;">{{msg.titone}}</view>
		<view>{{msg.onemsg}}</view>
		<view style="margin: 2%;">{{msg.tittwo}}</view>
		<image :src="img"></image>
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
