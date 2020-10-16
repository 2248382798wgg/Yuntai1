<template>
	<view style="display: flex;width: 100%;justify-content: center;">
		<view v-if="ner ==''">没有更多内容</view>
		<view v-else="" style="background-color: #FFFFFF;width: 90%;height: 166px;box-shadow: 5px 5px 5px #888888;border-radius: 5px;">
			<view style="display: flex;">
				<image style="width: 46%;height: 127px;border-radius: 5px;margin: 5%;" :src="ner.img"></image>
				<view style="margin-top: 5%;font-size: 15px;">{{ner.name}}
					<view style="margin-top: 5%;"> 数量 {{ner.len}}</view>
				</view>

			</view>



		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				ner: ''
			}
		},
		methods: {

		},
		onLoad(options) {
			var ner = JSON.parse(decodeURIComponent(options.data));
			this.ner = ner
			console.log(this.ner)
		}
	}
</script>

<style>

</style>
