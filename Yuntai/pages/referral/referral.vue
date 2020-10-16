<template>
	<view class="content">
			<view class="container">
				<view class="title">{{test.title}}</view>
				<view class="text">{{test.text}}</view>
				<view class="imgone">
					<image :src="test.imgone"></image>
				</view>
				<view class="container-text">
					<view class="fieldone">
						{{test.fieldone}}
					</view>
					<view class="fieldtwo">
						{{test.fieldtwo}}
					</view>
					<view class="eyes">
						{{test.eyes}}
					</view>
					<view class="fieldtwo">
						{{test.fieldthree}}
					</view>
					<view class="fieldtwo">
						{{test.fieldfour}}
					</view>
					<view class="fieldtwo">
						{{test.fieldfive}}
					</view>
					<view class="imgtwo">
						<image :src="test.imgtwo"></image>
					</view>
					<view class="eyes">
						{{test.heart}}
					</view>
					<view class="fieldtwo">
						{{test.fieldsix}}
					</view>
					<view class="imgone">
						<image :src="test.imgthree"></image>
					</view>
					<view class="eyes">
						{{test.sum}}
					</view>
					<view class="imgtwo">
						{{test.fieldseven}}
					</view>
					<view class="imgtwo">
						{{test.fieldeight}}
					</view>
					<view class="imgone">
						<image :src="test.imgfour"></image>
					</view>
					<view class="eyes">
						{{test.living}}
					</view>
					<view class="imgtwo">
						{{test.fieldnight}}
					</view>
					<view class="imgtwo">
						{{test.fieldten}}
					</view>
					<view class="imgone">
						<image :src="test.imgfive"></image>
					</view>
					<view class="eyes">
						{{test.min}}
					</view>
					<view class="imgtwo">
						{{test.fieldsone}}
					</view>
					<view class="imgtwo">
						{{test.fieldstwo}}
					</view>
					<view class="imgone">
						<image :src="test.imgsix"></image>
					</view>
					<view class="titletwo">{{test.titletwo}}</view>
					<view class="imgtwo">
						{{test.fieldsthree}}
					</view>
					<view class="imgone">
						<image :src="test.imgseven"></image>
					</view>
					<view class="imgone">
						<image :src="test.imgeight"></image>
					</view>
					<view class="titlethree">{{test.titlethree}}</view>
					<view class="imgtwo">
						{{test.fieldsfour}}
					</view>
					<view class="imgone">
						<image :src="test.imgnight"></image>
					</view>
					<view class="eyes">
						{{test.security}}
					</view>
					<view class="imgtwo">
						{{test.fieldsfive}}
					</view>
					<view class="eyes">
						{{test.running}}
					</view>
					<view class="imgtwo">
						{{test.fieldssix}}
					</view>
					<view class="eyes">
						{{test.convenient}}
					</view>
					<view class="imgtwo">
						{{test.fieldsseven}}
					</view>
					<view class="imgtwo">
						{{test.fieldseight}}
					</view>
					<view class="titlefour">{{test.titlefour}}</view>
					<view class="imgtwo">
						{{test.fieldsnight}}
					</view>
					<view class="imgone">
						<image :src="test.imgten"></image>
					</view>
					<view class="imgtwo">
						{{test.fieldsten}}
					</view>
					<view class="imgone">
						<image :src="test.imgselevent"></image>
					</view>
					<view class="titlefive">{{test.titlefive}}</view>
					<view class="imgtwo">
						{{test.fieldsten}}
					</view>
					<view class="imgone">
						<image :src="test.imgtwot"></image>
					</view>
					<view class="eyes">
						{{test.work}}
					</view>
					<view class="imgtwo">
						{{test.fieldstwos}}
					</view>
					<view class="imgone">
						<image :src="test.imgthreee"></image>
					</view>
					<view class="imgtwo">
						{{test.fieldsthrees}}
					</view><view class="imgtwo">
						{{test.fieldsfours}}
					</view>
					<view class="imgtwo">
						{{test.fieldsfives}}
					</view>
					<view class="imgtwo">
						{{test.fieldssixs}}
					</view>
					<view class="imgtwo">
						{{test.fieldssevens}}
					</view>
					<view class="imgtwo">
						{{test.fieldseights}}
					</view>
					<view class="imgtwo">
						{{test.fieldsnights}}
					</view>
					<view class="titlesix">{{test.titlesix}}</view>
					<view class="imgtwo">
						{{test.fieldssone}}
					</view>
					<view class="imgone">
						<image :src="test.imgfourr"></image>
					</view>
					<view class="imgthree">
						{{test.fieldsstwo}}
					</view>
				</view>
			</view>
		</view>
</template>

<script>
	import json from '../../testdata/index.json'; //引入js文件
	export default {
		data() {
			return {
				test:''
			}
		},
		methods: {
			
		},
		onLoad() {
			this.test = json.introduce;
		}
	}
</script>

<style>
	.container {
		width: 90%;
		margin-left: 5%;
		margin-top: 4%;
	}

	.title {
		font-size: 55rpx;
		color: #555555;
	}

	.text {
		font-size: 45rpx;
		color: #555555;
		margin-top: 4%;
	}

	.imgone {
		margin-top: 5%;
	}

	.imgone image {
		width: 100%
	}
	.container-text{
		font-size: 28rpx;
		color: #707070;
		line-height: 24px;
	}
	.fieldone {
		margin-top: 2%;
	}

	.fieldtwo {
		margin-top: 3%;
	}
	.eyes {
		margin-top: 3%;
		font-size: 33rpx;
		color: #333333;
		font-weight: 500;
	}
	.imgtwo {
		margin-top: 4%;
	}
	.imgtwo image {
		width: 100%;
		height: 160px;
	}
	.titletwo{
		margin-top: 4%;
		font-size: 55rpx;
		color: #555555;
	}
	.titlethree{
		margin-top: 4%;
		font-size: 55rpx;
		color: #555555;
	}
	.titlefour{
		margin-top: 5%;
		font-size: 55rpx;
		color: #555555;
		margin-bottom: 2%;
	}
	.titlefive{
		margin-top: 5%;
		font-size: 55rpx;
		color: #555555;
		margin-bottom: 2%;
	}
	.titlesix{
		margin-top: 5%;
		font-size: 55rpx;
		color: #555555;
		padding-bottom: 2%;
	}
	.imgthree{
		margin-top: 4%;
		margin-bottom: 4%;
	}
</style>
